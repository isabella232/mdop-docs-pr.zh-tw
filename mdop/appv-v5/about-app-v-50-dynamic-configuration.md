---
title: 關於 App-V 5.0 動態組態
description: 關於 App-V 5.0 動態組態
author: dansimp
ms.assetid: 88afaca1-68c5-45c4-a074-9371c56b5804
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0294a60570d6dea99193c8bd411639c4888ae6b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800738"
---
# 關於 App-V 5.0 動態組態


您可以使用動態設定來自訂使用者的 app-v 5.0 套件。 使用下列資訊來建立或編輯現有的動態設定檔。

當您編輯動態配置檔案時，它會自訂將 App-v 5.0 套件用於使用者或群組的方式。 這有助於透過移除需要使用所需設定來重新排序套件的方式，為套件自訂提供更簡單的方法，並提供一種將套件內容和自訂設定保持在獨立的方法。

## [高級]：動態設定


虛擬應用程式套件包含提供套件所有核心資訊的資訊清單。 此資訊包括套件設定的預設值，並決定最基本形式的設定（沒有其他自訂）。 如果您想要針對特定的使用者或群組調整這些預設值，您可以建立及編輯下列檔案：

-   使用者設定檔

-   部署設定檔

Previous .xml 檔案會指定套件設定，並允許對套件進行自訂，而不會直接影響套件。 建立套件時，sequencer 會使用封裝資訊清單資料自動產生預設的部署和使用者設定 .xml 檔案。 因此，這些自動產生的設定檔只會反映出套件 innately 的預設設定，就像在排序期間設定的專案。 如果您將這些設定檔案套用到由排序器所產生的表單中的套件，套件將會有其資訊清單所產生的預設設定。 這可讓您在必須變更任何預設值的情況下，為您提供套件專用的範本以開始使用。

**記事** 下列資訊只能用來修改 sequencer 產生的設定檔案，以自訂套件，以符合特定的使用者或群組需求。

 

### 動態設定檔內容

設定檔中的所有新增、刪除及更新，都需要與套件的資訊清單資訊所指定的預設值建立關聯。 請參閱下表：

<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>使用者配置 .xml 檔案</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署配置 .xml 檔案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>封裝資訊清單</p></td>
</tr>
</tbody>
</table>

 

上表代表檔案的閱讀方式。 第一個專案代表最後讀取的內容，因此其內容優先。 因此，所有套件本身都包含並提供套件資訊清單的預設設定。 如果套用了含自訂設定的部署配置 .xml 檔案，則會覆寫套件資訊清單預設值。 如果先套用自訂設定的使用者配置 .xml 檔案，就會覆寫部署配置和套件資訊清單預設值。

下列清單會顯示兩種檔案類型的詳細資訊：

-   **使用者設定檔（UserConfig）** -可讓您指定或修改套件的自訂設定。 當套件部署到執行 App-v 5.0 用戶端的電腦時，這些設定將會套用到特定使用者。

-   **部署設定檔（DeploymentConfig）** -可讓您指定或修改套件的預設設定。 當套件部署到執行 App-v 5.0 用戶端的電腦時，這些設定將會套用給所有使用者。

若要針對電腦上的一組特定使用者自訂套件的設定，或進行將套用到本機使用者位置（例如 HKCU）的變更，請使用 UserConfig 檔案。 若要針對電腦上的所有使用者修改套件的預設設定，或進行將套用到全域位置的變更（例如 HKEY \ _LOCAL \ _MACHINE 和 [所有使用者] 資料夾），應使用 DeploymentConfig 檔案。

UserConfig 檔案提供的設定可套用至單一使用者，而不會影響用戶端上的任何其他使用者：

-   每個使用者將整合到原生系統的延伸：-快速鍵、檔案類型關聯、URL 協定、AppPaths、軟體用戶端及 COM

-   虛擬子系統：-應用程式物件、環境變數、註冊表修改、服務和字型

-   腳本（僅限使用者內容）

-   管理頒發機構（以 App-v 4.6 控制套件共同存在）

DeploymentConfig 檔案提供兩個區段中的配置設定，其中一個相對於電腦內容，另一個相對於使用者內容，提供與上述 UserConfig 清單中相同的功能：

-   上述所有 UserConfig 設定

-   只能全域針對所有使用者套用的延伸

-   可針對全域電腦位置設定的虛擬子系統，例如 registry

-   產品來源 URL

-   腳本（僅限電腦內容）

-   終止子進程的控制項

### 檔結構

App-v 5.0 動態設定檔的結構將在下一節中說明。

### 動態使用者設定檔

**頁首**-動態使用者設定檔案的標頭如下所示：

&lt;？ xml 版本 = "1.0" encoding = "utf-8"？ &gt; &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

**PackageId**的值與資訊清單檔案中的相同。

本文-動態使用者設定檔**的主體可以**包含在資訊清單檔案中定義的所有應用程式延伸點，以及設定虛擬應用程式的相關資訊。 本文中有四個小節可供使用：

1. **應用程式**-套件內的資訊清單檔案中所包含的所有應用程式延伸都是由應用程式識別碼所指派，也會在資訊清單檔案中定義。 這可讓您在套件中啟用或停用指定應用程式的所有延伸。 **應用程式識別碼**必須存在於資訊清單檔案中，否則將會被忽略。

   &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

   &lt;應用程式&gt;

   &lt;!--不能在原則中定義任何新的應用程式。 AppV 用戶端將會忽略資訊清單檔中不存在的任何應用程式識別碼，&gt;

   &lt;應用程式識別碼 = "{a56fa627-c35f-4a01-9e79-7d36aed8225a}" 已啟用 = "false"&gt;

   &lt;/Application&gt;

   &lt;/Applications&gt;

   …

   &lt;/UserConfiguration&gt;

2. **子系統**： AppExtensions 和其他子系統會以子節點的方式排列在子系統的下方 &lt; &gt; ：

   &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

   &lt;分系統&gt;

   ..

   &lt;/Subsystems&gt;

   ..

   &lt;/UserConfiguration&gt;

   每個子系統都可以使用「**enabled**」屬性啟用/停用。 以下是各種子系統和用法範例。

   **長度**

   某些子系統（延伸分系統）控制延伸。 這些子系統包括：-快速鍵、檔案類型關聯、URL 協定、AppPaths、軟體用戶端及 COM

   您可以獨立使用內容來啟用和停用延伸子系統。  因此，如果已啟用快速鍵，用戶端將會使用包含在資訊清單中的快速鍵（預設）。 每個擴展子系統都可以包含 &lt; 擴充 &gt; 節點。 如果這個子項目存在，用戶端將略過該子系統的資訊清單檔案中的內容，只使用設定檔中的內容。

   使用 [快速鍵] 子系統的範例：

   1.  如果使用者在動態或部署設定檔中定義此專案：

                                    **&lt;Shortcuts  Enabled="true"&gt;**

                                                **&lt;Extensions&gt;**

                                                 ...

                                                **&lt;/Extensions&gt;**

                                    **&lt;/Shortcuts&gt;**

                         Content in the manifest will be ignored.   

   2.  如果使用者只定義下列各項：

                                   **&lt;Shortcuts  Enabled="true"/&gt;**

                         Then the content in the Manifest will be integrated during publishing.

   3.  如果使用者定義下列各項：

                                  **&lt;Shortcuts  Enabled="true"&gt;**

                                                **&lt;Extensions/&gt;**

                                    **&lt;/Shortcuts&gt;**

   接著，資訊清單中的所有快速鍵仍會被忽略。 將不會整合任何快速鍵。

   支援的延伸子系統如下：

   **快速鍵：** 這會控制將整合到本機系統中的快捷方式。 以下是兩個快速鍵的範例：

   &lt;分系統&gt;

   &lt;快速鍵已啟用 = "true"&gt;

     &lt;Extensions&gt;

       &lt;Extension Category="AppV.Shortcut"&gt;

         &lt;Shortcut&gt;

           &lt;File&gt;\[{Common Programs}\]\\Microsoft Contoso\\Microsoft ContosoApp Filler 2010.lnk&lt;/File&gt;

           &lt;Target&gt;\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE&lt;/Target&gt;

           &lt;Icon&gt;\[{Windows}\]\\Installer\\{90140000-0011-0000-0000-0000000FF1CE}\\inficon.exe&lt;/Icon&gt;

           &lt;Arguments /&gt;

           &lt;WorkingDirectory /&gt;

           &lt;AppUserModelId&gt;ContosoApp.Filler.3&lt;/AppUserModelId&gt;

           &lt;Description&gt;Fill out dynamic forms to gather and reuse information throughout the organization using Microsoft ContosoApp.&lt;/Description&gt;

           &lt;Hotkey&gt;0&lt;/Hotkey&gt;

           &lt;ShowCommand&gt;1&lt;/ShowCommand&gt;

           &lt;ApplicationId&gt;\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE&lt;/ApplicationId&gt;

         &lt;/Shortcut&gt;

     &lt;/Extension&gt;

     &lt;延伸類別 = "AppV. 快捷方式"&gt;

       &lt;Shortcut&gt;

         &lt;File&gt;\[{AppData}\]\\Microsoft\\Contoso\\Recent\\Templates.LNK&lt;/File&gt;

         &lt;Target&gt;\[{AppData}\]\\Microsoft\\Templates&lt;/Target&gt;

         &lt;Icon /&gt;

         &lt;Arguments /&gt;

         &lt;WorkingDirectory /&gt;

         &lt;AppUserModelId /&gt;

         &lt;Description /&gt;

         &lt;Hotkey&gt;0&lt;/Hotkey&gt;

         &lt;ShowCommand&gt;1&lt;/ShowCommand&gt;

         &lt;!-- Note the ApplicationId is optional --&gt;

       &lt;/Shortcut&gt;

     &lt;/Extension&gt;

    &lt;/Extensions&gt;

   &lt;/Shortcuts&gt;

   **檔案類型關聯：** 將檔案類型與程式建立關聯，以供預設開啟，以及設定操作功能表。 （您也可以使用此 susbsystem 設定 MIME 類型）。 範例檔案類型關聯如下所示：

   &lt;FileTypeAssociations Enabled = "true"&gt;

   &lt;Extensions&gt;

     &lt;延伸類別 = "AppV FileTypeAssociation"&gt;

       &lt;FileTypeAssociation&gt;

         &lt;FileExtension MimeAssociation="true"&gt;

         &lt;Name&gt;.docm&lt;/Name&gt;

         &lt;ProgId&gt;contosowordpad.DocumentMacroEnabled.12&lt;/ProgId&gt;

         &lt;PerceivedType&gt;document&lt;/PerceivedType&gt;

         &lt;ContentType&gt;application/vnd.ms-contosowordpad.document.macroEnabled.12&lt;/ContentType&gt;

         &lt;OpenWithList&gt;

           &lt;ApplicationName&gt;wincontosowordpad.exe&lt;/ApplicationName&gt;

         &lt;/OpenWithList&gt;

        &lt;OpenWithProgIds&gt;

           &lt;ProgId&gt;contosowordpad.8&lt;/ProgId&gt;

         &lt;/OpenWithProgIds&gt;

         &lt;ShellNew&gt;

           &lt;Command /&gt;

           &lt;DataBinary /&gt;

           &lt;DataText /&gt;

           &lt;FileName /&gt;

           &lt;NullFile&gt;true&lt;/NullFile&gt;

           &lt;ItemName /&gt;

           &lt;IconPath /&gt;

           &lt;MenuText /&gt;

           &lt;Handler /&gt;

         &lt;/ShellNew&gt;

       &lt;/FileExtension&gt;

       &lt;ProgId&gt;

          &lt;Name&gt;contosowordpad.DocumentMacroEnabled.12&lt;/Name&gt;

           &lt;DefaultIcon&gt;\[{Windows}\]\\Installer\\{90140000-0011-0000-0000-0000000FF1CE}\\contosowordpadicon.exe,15&lt;/DefaultIcon&gt;

           &lt;Description&gt;Blah Blah Blah&lt;/Description&gt;

           &lt;FriendlyTypeName&gt;\[{FOLDERID\_ProgramFilesX86}\]\\Microsoft Contoso 14\\res.dll,9182&lt;/FriendlyTypeName&gt;

           &lt;InfoTip&gt;\[{FOLDERID\_ProgramFilesX86}\]\\Microsoft Contoso 14\\res.dll,1424&lt;/InfoTip&gt;

           &lt;EditFlags&gt;0&lt;/EditFlags&gt;

           &lt;ShellCommands&gt;

             &lt;DefaultCommand&gt;Open&lt;/DefaultCommand&gt;

             &lt;ShellCommand&gt;

                &lt;ApplicationId&gt;{e56fa627-c35f-4a01-9e79-7d36aed8225a}&lt;/ApplicationId&gt;

                &lt;Name&gt;Edit&lt;/Name&gt;

                &lt;FriendlyName&gt;&Edit&lt;/FriendlyName&gt;

                &lt;CommandLine&gt;"\[{PackageRoot}\]\\Contoso\\WINcontosowordpad.EXE" /vu "%1"&lt;/CommandLine&gt;

             &lt;/ShellCommand&gt;

             &lt;/ShellCommand&gt;

               &lt;ApplicationId&gt;{e56fa627-c35f-4a01-9e79-7d36aed8225a}&lt;/ApplicationId&gt;

               &lt;Name&gt;Open&lt;/Name&gt;

               &lt;FriendlyName&gt;&Open&lt;/FriendlyName&gt;

               &lt;CommandLine&gt;"\[{PackageRoot}\]\\Contoso\\WINcontosowordpad.EXE" /n "%1"&lt;/CommandLine&gt;

               &lt;DropTargetClassId /&gt;

               &lt;DdeExec&gt;

                 &lt;Application&gt;mscontosowordpad&lt;/Application&gt;

                 &lt;Topic&gt;ShellSystem&lt;/Topic&gt;

                 &lt;IfExec&gt;\[SHELLNOOP\]&lt;/IfExec&gt;

                 &lt;DdeCommand&gt;\[SetForeground\]\[ShellNewDatabase "%1"\]&lt;/DdeCommand&gt;

               &lt;/DdeExec&gt;

             &lt;/ShellCommand&gt;

           &lt;/ShellCommands&gt;

         &lt;/ProgId&gt;

        &lt;/FileTypeAssociation&gt;

      &lt;/Extension&gt;

     &lt;/Extensions&gt;

     &lt;/FileTypeAssociations&gt;

   **URL 通訊協定**：這會控制與用戶端電腦的本機登錄（例如「mailto：」）整合的 Url 通訊協定。

   &lt;URLProtocols Enabled = "true"&gt;

   &lt;Extensions&gt;

   &lt;延伸類別 = "AppV URLProtocol"&gt;

   &lt;URLProtocol&gt;

     &lt;姓名 &gt; mailto &lt; /Name&gt;

     &lt;ApplicationURLProtocol&gt;

     &lt;DefaultIcon &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE，-9403 &lt; /DefaultIcon&gt;

     &lt;EditFlags &gt; 2 &lt; /EditFlags&gt;

     &lt;說明&gt;

     &lt;AppUserModelId&gt;

     &lt;FriendlyTypeName /&gt;

     &lt;提示&gt;

   &lt;SourceFilter /&gt;

     &lt;ShellFolder /&gt;

     &lt;WebNavigableCLSID /&gt;

     &lt;ExplorerFlags &gt; 2 &lt; /ExplorerFlags&gt;

     &lt;CLSID&gt;

     &lt;ShellCommands&gt;

     &lt;DefaultCommand &gt; 開啟 &lt; /DefaultCommand&gt;

     &lt;ShellCommand&gt;

     &lt;ApplicationId &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationId&gt;

     &lt;名稱 &gt; 開啟 &lt; /Name&gt;

     &lt;命令列 &gt; \ [{ProgramFilesX86} \\Microsoft Contoso\\Contoso\\contosomail.EXE "-c OEP]。注意/m "%1" &lt; /CommandLine&gt;

     &lt;DropTargetClassId /&gt;

     &lt;友好&gt;

     &lt;延伸 &gt; 0 &lt; /Extended&gt;

     &lt;LegacyDisable &gt; 0 &lt; /LegacyDisable&gt;

     &lt;SuppressionPolicy &gt; 2 &lt; /SuppressionPolicy&gt;

      &lt;DdeExec&gt;

     &lt;NoActivateHandler /&gt;

     &lt;應用程式 &gt; contosomail &lt; /Application&gt;

     &lt;主題 &gt; ShellSystem &lt; /Topic&gt;

     &lt;IfExec &gt; \ [SHELLNOOP \] &lt; /IfExec&gt;

     &lt;DdeCommand &gt; \ [SetForeground \] \ [ShellNewDatabase "%1" \] &lt; /DdeCommand&gt;

     &lt;/DdeExec&gt;

     &lt;/ShellCommand&gt;

     &lt;/ShellCommands&gt;

     &lt;/ApplicationURLProtocol&gt;

     &lt;/URLProtocol&gt;

     &lt;/Extension&gt;

     &lt;/Extension&gt;

     &lt;/URLProtocols&gt;

   **軟體用戶端**：允許 App 以電子郵件用戶端、新聞閱讀程式、媒體播放機的方式登錄，並使應用程式在 [設定程式存取及電腦預設值] UI 中顯示。 在大多數情況下，您應該只需要啟用和停用。 如果您想讓其他用戶端（除了該用戶端除外），也可以使用此控制項來啟用和停用電子郵件用戶端。

   &lt;SoftwareClients Enabled = "true"&gt;

     &lt;ClientConfiguration EmailEnabled = "false"/&gt;

   &lt;/SoftwareClients&gt;

   AppPaths：-如果您使用 apppath 名稱 "myapp" 登錄應用程式範例 contoso.exe，它可讓您在 [執行] 功能表下輸入 "myapp"，並開啟 [contoso.exe]。

   &lt;AppPaths Enabled = "true"&gt;

   &lt;Extensions&gt;

   &lt;延伸類別 = "AppV AppPath"&gt;

   &lt;AppPath&gt;

     &lt;ApplicationId &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationId&gt;

     &lt;名稱 &gt;contosomail.exe&lt; /Name&gt;

     &lt;ApplicationPath &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationPath&gt;

     &lt;PATHEnvironmentVariablePrefix /&gt;

     &lt;CanAcceptUrl &gt; false &lt; /CanAcceptUrl&gt;

     &lt;SaveUrl /&gt;

   &lt;/AppPath&gt;

   &lt;/Extension&gt;

   &lt;/Extensions&gt;

   &lt;/AppPaths&gt;

   **COM**：允許應用程式註冊本機 COM 伺服器。 Mode 可以是整合、隔離或關閉。 Isol 時。

   &lt;COM Mode = "獨立主機"/&gt;

   **其他設定**：

   除了延伸之外，也可以啟用/停用或編輯其他子系統：

   **虛擬核心物件**：

   &lt;已啟用的物件 = "false"/&gt;

   **虛擬**機：如果您想要在 HKCU 的虛擬機器中設定登錄，就會使用

   &lt;Registry 已啟用 = "true"&gt;

   &lt;帶有&gt;

   &lt;索引鍵路徑 = "\\REGISTRY\\USER\\\ [{AppVCurrentUserSID} \] \\Software\\ABC"&gt;

   &lt;數值型別 = "REG \ _SZ" Name = "Bar" 資料 = "NewValue"/&gt;

    &lt;/Key&gt;

     &lt;索引鍵路徑 = "\\REGISTRY\\USER\\\ [{AppVCurrentUserSID} \] \\Software\\EmptyKey"/&gt;

    &lt;/Include&gt;

   &lt;Delete&gt;

     &lt;/Registry&gt;

   **虛擬檔案系統**

         &lt;FileSystem Enabled="true" /&gt;

   **虛擬字型**

         &lt;Fonts Enabled="false" /&gt;

   **虛擬環境變數**

   &lt;EnvironmentVariables Enabled = "true"&gt;

   &lt;帶有&gt;

          &lt;Variable Name="UserPath" Value="%path%;%UserProfile%" /&gt;

          &lt;Variable Name="UserLib" Value="%UserProfile%\\ABC" /&gt;

          &lt;/Include&gt;

         &lt;Delete&gt;

          &lt;Variable Name="lib" /&gt;

           &lt;/Delete&gt;

           &lt;/EnvironmentVariables&gt;

   **虛擬服務**

         &lt;Services Enabled="false" /&gt;

3. **UserScripts** –腳本可以用來設定或變更虛擬環境，以及在部署或移除時執行腳本（在應用程式執行之前），也可以用來在應用程式終止之後，使用這些腳本來「清理」環境。 請參照排序器輸出的範例使用者設定檔，以查看範例腳本。 下面的 [腳本] 區段提供了有關可使用的各種觸發程式的詳細資訊。

4. **ManagingAuthority** –可在同一部電腦上共同擁有套件的兩個版本，其中一個部署到 app-v 4.6，另一個部署在 app-v 5.0 上。 若要允許 App-v vNext 接管命名套件的 App-v 4.6 延伸點，請在 UserConfig 檔案中輸入下列內容（其中 PackageName 是 App-v 4.6 中的套件 GUID）：

   &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = "032630c0-b8e2-417c-acef-76fc5297fe81"/&gt;

### 動態部署設定檔

[**標頭**]-部署設定檔的標頭如下所示：

&lt;？ xml 版本 = "1.0" encoding = "utf-8"？ &gt; &lt;DeploymentConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration"&gt> ;

**PackageId**的值與資訊清單檔案中的相同。

**Body** -部署設定檔的主體包含兩個區段：

-   [使用者設定] 區段–可與前一節所述的使用者配置檔案相同的內容。 當套件發佈至使用者時，此區段中的任何 appextensions 設定設定將會覆寫套件內的資訊清單中的對應設定，除非也提供使用者設定檔。 如果同時提供了 UserConfig 檔案，則會使用它，而不是部署設定檔中的使用者設定。 如果套件是全域發佈的，則只有部署設定檔的內容會與資訊清單搭配使用。

-   [電腦設定] 區段–包含只能針對整個電腦設定的資訊，不適用於電腦上的特定使用者。 例如，HKEY \ _LOCAL，在 VFS 中 _MACHINE 登錄機碼。

&lt;DeploymentConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration"&gt> ;

&lt;UserConfiguration&gt;

  ..

&lt;/UserConfiguration&gt;

&lt;MachineConfiguration&gt;

..

&lt;/MachineConfiguration&gt;

..

&lt;/MachineConfiguration&gt;

&lt;/DeploymentConfiguration&gt;

**使用者**設定-使用先前的 [**動態使用者設定檔**] 區段，取得部署設定檔之 [使用者配置] 區段中所提供之設定的相關資訊。

電腦設定-部署設定檔的 [電腦設定] 區段是用來設定只能針對整個電腦設定的資訊，而不是電腦上的特定使用者。 例如，HKEY \ _LOCAL \ _MACHINE 虛擬機器中的登錄機碼。 這個元素下允許有四個子區段

1.  **子系統**： AppExtensions 和其他子系統會以子節點的方式排列在 [子系統] 底下 &lt; &gt; ：

    &lt;MachineConfiguration&gt;

      &lt;分系統&gt;

      ..

      &lt;/Subsystems&gt;

    ..

    &lt;/MachineConfiguration&gt;

    下一節會顯示各種子系統和用法範例。

    **延伸**：

    一些只能套用至所有使用者的分系統（延伸子系統）控制延伸。 子系統是應用程式功能。 因為這只能套用至所有使用者，所以必須以全域方式發佈套件，才能將這類延伸類型整合到本機系統中。 適用于使用者設定中延伸之控制項與設定的規則，也會套用到 MachineConfiguration 區段中的功能。

    **應用程式功能**：由 Windows 作業系統介面中的預設程式使用。 可讓應用程式自行登錄，以開啟特定的副檔名（例如 [開始] 功能表 internet 瀏覽器槽的 contender），就能開啟特定的 windows MIME 類型。此延伸也會讓虛擬應用程式顯示在 [設定預設程式] UI 中。：

    &lt;ApplicationCapabilities Enabled = "true"&gt;

      &lt;Extensions&gt;

       &lt;延伸類別 = "AppV ApplicationCapabilities"&gt;

        &lt;ApplicationCapabilities&gt;

         &lt;ApplicationId&gt;\[{PackageRoot}\]\\LitView\\LitViewBrowser.exe&lt;/ApplicationId&gt;

         &lt;Reference&gt;

          &lt;Name&gt;LitView Browser&lt;/Name&gt;

          &lt;Path&gt;SOFTWARE\\LitView\\Browser\\Capabilities&lt;/Path&gt;

         &lt;/Reference&gt;

       &lt;CapabilityGroup&gt;

        &lt;Capabilities&gt;

         &lt;Name&gt;@\[{ProgramFilesX86}\]\\LitView\\LitViewBrowser.exe,-12345&lt;/Name&gt;

         &lt;Description&gt;@\[{ProgramFilesX86}\]\\LitView\\LitViewBrowser.exe,-12346&lt;/Description&gt;

         &lt;Hidden&gt;0&lt;/Hidden&gt;

         &lt;EMailSoftwareClient&gt;Lit View E-Mail Client&lt;/EMailSoftwareClient&gt;

         &lt;FileAssociationList&gt;

          &lt;FileAssociation Extension=".htm" ProgID="LitViewHTML" /&gt;

          &lt;FileAssociation Extension=".html" ProgID="LitViewHTML" /&gt;

          &lt;FileAssociation Extension=".shtml" ProgID="LitViewHTML" /&gt;

         &lt;/FileAssociationList&gt;

         &lt;MIMEAssociationList&gt;

          &lt;MIMEAssociation Type="audio/mp3" ProgID="LitViewHTML" /&gt;

          &lt;MIMEAssociation Type="audio/mpeg" ProgID="LitViewHTML" /&gt;

         &lt;/MIMEAssociationList&gt;

        &lt;URLAssociationList&gt;

          &lt;URLAssociation Scheme="http" ProgID="LitViewHTML.URL.http" /&gt;

         &lt;/URLAssociationList&gt;

         &lt;/Capabilities&gt;

      &lt;/CapabilityGroup&gt;

       &lt;/ApplicationCapabilities&gt;

      &lt;/Extension&gt;

    &lt;/Extensions&gt;

    &lt;/ApplicationCapabilities&gt;

    **其他設定**：

    除了延伸之外，還可以編輯其他子系統：

    **電腦範圍的虛擬**登錄：當您想要在 HKEY \ _Local 中設定虛擬機器碼時，請使用 \ _Machine

    &lt;登錄&gt;

    &lt;帶有&gt;

      &lt;索引鍵路徑 = "\\REGISTRY\\Machine\\Software\\ABC"&gt;

        &lt;Value Type="REG\_SZ" Name="Bar" Data="Baz" /&gt;

       &lt;/Key&gt;

      &lt;索引鍵路徑 = "\\REGISTRY\\Machine\\Software\\EmptyKey"/&gt;

     &lt;/Include&gt;

    &lt;Delete&gt;

    &lt;/Registry&gt;

    **電腦範圍的虛擬核心物件**

    &lt;物件&gt;

    &lt;NotIsolate&gt;

       &lt;物件名稱 = "testObject"/&gt;

     &lt;/NotIsolate&gt;

    &lt;/Objects&gt;

2.  **ProductSourceURLOptOut**：指示套件的 URL 是否可透過 PackageSourceRoot 全域修改（以支援分支辦公室案例）。 預設值為 false，設定變更會在下一次啟動時生效。  

    &lt;MachineConfiguration&gt;

      .. 

      &lt;ProductSourceURLOptOut Enabled = "true"/&gt;

      ..

    &lt;/MachineConfiguration&gt;

3.  **MachineScripts** –套件可以設定為在部署、發佈或移除時執行腳本。 請參照排序器所產生的範例部署設定檔，以查看範例腳本。 下面的 [腳本] 區段提供了有關可使用的各種觸發程式的詳細資訊

4.  **TerminateChildProcess**：-可以指定應用程式可執行檔，其子進程會在應用程式 exe 進程終止時終止。

    &lt;MachineConfiguration&gt;

      ..   

      &lt;TerminateChildProcesses&gt;

        &lt;Application Path="\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE" /&gt;

        &lt;Application Path="\[{PackageRoot}\]\\LitView\\LitViewBrowser.exe" /&gt;

        &lt;Application Path="\[{ProgramFilesX86}\]\\Microsoft Contoso\\Contoso\\contosomail.EXE" /&gt;

      &lt;/TerminateChildProcesses&gt;

      ..

    &lt;/MachineConfiguration&gt;

### 指令碼

下表說明各種腳本事件以及它們可以在其中執行的內容。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">腳本執行時間</th>
<th align="left">可在部署配置中指定</th>
<th align="left">可在使用者配置中指定</th>
<th align="left">可以在套件的虛擬環境中執行</th>
<th align="left">可以在特定應用程式的內容中執行</th>
<th align="left">在系統/使用者內容中執行：（部署設定、使用者配置）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AddPackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（系統、不適用）</p></td>
</tr>
<tr class="even">
<td align="left"><p>PublishPackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（系統、使用者）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UnpublishPackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（系統、使用者）</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（系統、不適用）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartProcess</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>（使用者、使用者）</p></td>
</tr>
<tr class="even">
<td align="left"><p>ExitProcess</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>（使用者、使用者）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartVirtualEnvironment</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p>（使用者、使用者）</p></td>
</tr>
<tr class="even">
<td align="left"><p>TerminateVirtualEnvironment</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（使用者、使用者）</p></td>
</tr>
</tbody>
</table>

 

### 使用 App-v 5.0 資訊清單檔案建立動態設定檔

您可以使用下列三種方法的其中一種來建立動態設定檔：手動、使用 App-v 5.0 管理主控台或對套件進行排序，這兩個範例檔案就會產生。

如需如何使用 App-v 5.0 管理主控台建立檔案的詳細資訊，請參閱[如何使用 app-v 5.0 管理主控台來建立自訂的設定檔](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)。

若要手動建立檔案，前幾節中的資訊可以合併成單一檔案。 我們建議您使用排序器所產生的檔案。






## 相關主題


[如何使用 PowerShell 來套用部署設定檔案](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

[如何使用 PowerShell 來套用使用者設定檔案](how-to-apply-the-user-configuration-file-by-using-powershell.md)

[App-V 5.0 作業](operations-for-app-v-50.md)

 

 





