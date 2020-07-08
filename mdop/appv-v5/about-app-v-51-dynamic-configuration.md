---
title: 關於 App-V 5.1 動態設定
description: 您可以使用動態設定來自訂使用者的 app-v 5.1 套件。 使用下列資訊來建立或編輯現有的動態設定檔。
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/28/2018
ms.author: dansimp
ms.openlocfilehash: ec8a25da6e139ac329810b1e04f7097cadaa6ab4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800724"
---
# 關於 App-V 5.1 動態設定 
在動態設定中，您可以編輯動態設定檔案，來自訂使用者或群組對 App-v 5.1 套件的執行方式。 套件自訂移除需要使用所需設定 resequence 套件。  它也提供一種將套件內容和自訂設定保持在獨立的方式。

虛擬應用程式套件包含提供套件所有核心資訊的資訊清單。 此資訊包括套件設定的預設值，並決定最基本形式的設定（沒有其他自訂）。 

建立套件時，排序器會自動使用套件資訊清單資料來產生預設的部署和使用者配置 .xml 檔案。 因此，這些產生的檔案會反映在排序期間設定的預設設定。 如果您將這些檔案套用到由排序器所產生的表單中的套件，則套件的預設設定會與它們的資訊清單來自它們的相同。 

如有需要，請使用這些產生的檔案進行變更，而不會直接影響套件。 如果您想要新增、刪除或更新設定檔，請在資訊清單資訊中變更預設值。

>[!TIP]
>檔案讀取順序如下：<ul><li>UserConfig.xml</li><li>DeploymentConfig.xml</li><li>Manifest</li></ul><p>第一個專案代表最後讀取的內容。 因此，其內容優先，且所有套件本身都包含並提供套件資訊清單中的預設設定。<ol><li> 如果自訂 DeploymentConfig.xml 檔案並套用自訂設定，套件資訊清單中的預設設定會被取代。 </li><li> 如果自訂 UserConfig.xml 並套用自訂的設定，則部署配置和套件資訊清單的預設設定會被取代。 </li></ol>

## 使用者設定檔內容（UserConfig.xml）
UserConfig 檔案提供將套件部署到執行 App-v 5.1 用戶端的電腦時，適用于特定使用者的設定設定。  這些設定不會影響用戶端上的任何其他使用者。

使用 UserConfig 檔案來指定或修改套件的自訂設定：

-   針對每位使用者將延伸整合到原生系統：快速鍵、檔案類型關聯、URL 協定、AppPaths、軟體用戶端及 COM
-   虛擬子系統：應用程式物件、環境變數、註冊表修改、服務和字型
-   腳本（僅限使用者內容）
-   管理頒發機構（以 App-v 4.6 控制套件共同存在）

### 標頭

動態使用者設定檔案的標頭如下所示：

```xml
<?xml version="1.0" encoding="utf-8"?><UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">
```

**PackageId**的值與資訊清單檔案中的相同。


### Body

動態使用者設定檔的主體可以包含資訊清單檔案中定義的所有應用程式延伸點，以及設定虛擬應用程式的資訊。 本文中有四個小節可供使用：

1.  **[應用程式](#applications)** 
2.  **[分系統](#subsystems)**
3.  **[UserScripts](#userscripts)**
4.  **[ManagingAuthority](#managingauthority)**

#### 應用程式

套件內的資訊清單檔案中包含的所有應用程式延伸都有指派的應用程式識別碼，您可以在資訊清單檔案中找到。 [應用程式識別碼] 可讓您啟用或停用套件中特定應用程式的所有延伸。 應用程式識別碼必須存在於資訊清單檔案中，否則會被略過。

```XML
<UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved"  xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">

<Applications>

<!--No new application can be defined in policy. AppV Client will ignore any application ID that is not also in the Manifest file-->

<Application Id="{a56fa627-c35f-4a01-9e79-7d36aed8225a}" Enabled="false">

</Application>

</Applications>

..

</UserConfiguration>
```

#### 分系統

AppExtensions 和其他子系統排列為子節點。

```XML
<UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">

<Subsystems>

..

</Subsystems>

..

</UserConfiguration>
```

您可以使用**Enabled**屬性來啟用或停用每個子系統。

**Extensions** 

某些子系統（延伸分系統）控制延伸。 這些子系統是快捷方式、檔案類型關聯、URL 協定、AppPaths、軟體用戶端及 COM。

您可以獨立使用內容來啟用和停用延伸子系統。 例如，如果您啟用 [快速鍵]，用戶端預設會使用包含在資訊清單中的快速鍵。 每個擴展子系統都可以包含一個 \<Extensions\> 節點。 如果這個子項目存在，用戶端會忽略該子系統的資訊清單檔案中的內容，只使用設定檔中的內容。 

_**範例：**_ 

- 如果您在 [使用者] 或 [部署] 設定檔中定義此選項，則會忽略資訊清單中的內容。

  ```XML

  <Shortcuts  Enabled="true"\>

  <Extensions>

  ...

  </Extensions>

  </Shortcuts>
  ```
- 如果您只定義下列內容，資訊清單中的內容會在發佈期間得到整合。

  ```XML

  <Shortcuts  Enabled="true"/>
  ```

- 如果您定義下列各項，資訊清單中的所有快速鍵仍會被忽略。 換句話說，沒有任何快速鍵會整合。

  ```XML

  <Shortcuts  Enabled="true">

     <Extensions/>

  </Shortcuts>
  ```

_**支援的延伸子系統：**_ 

**快捷方式**擴展子系統會控制哪些快速鍵會整合到本機系統中。  

```XML

<Subsystems>

<Shortcuts Enabled="true">

  <Extensions>

    <Extension Category="AppV.Shortcut">

      <Shortcut>

        <File>[{Common Programs}]\Microsoft Contoso\Microsoft ContosoApp Filler 2010.lnk</File>

        <Target>[{PackageRoot}]\Contoso\ContosoApp.EXE</Target>


      <Icon>[{Windows}]\Installer\{90140000-0011-0000-0000-0000000FF1CE}\inficon.exe</Icon>

        <Arguments />

        <WorkingDirectory />

        <AppUserModelId>ContosoApp.Filler.3</AppUserModelId>

        <Description>Fill out dynamic forms to gather and reuse information throughout the organization using Microsoft ContosoApp.</Description>

        <Hotkey>0</Hotkey>

        <ShowCommand>1</ShowCommand>

      <ApplicationId>[{PackageRoot}]\Contoso\ContosoApp.EXE</ApplicationId>

      </Shortcut>

  </Extension>

  <Extension Category="AppV.Shortcut">

    <Shortcut>

    <File>[{AppData}]\Microsoft\Contoso\Recent\Templates.LNK</File>

      <Target>[{AppData}]\Microsoft\Templates</Target>

      <Icon />

      <Arguments />

      <WorkingDirectory />

      <AppUserModelId />

      <Description />

      <Hotkey>0</Hotkey>

      <ShowCommand>1</ShowCommand>

      <!-- Note the ApplicationId is optional -->

    </Shortcut>

  </Extension>

 </Extensions>

</Shortcuts>
```

檔案類型**關聯**擴展子系統會將檔案類型與預設開啟的程式建立關聯，以及設定操作功能表。 

>[!TIP]
>您可以使用 MIME 類型來設定子系統。

```XML

<FileTypeAssociations Enabled="true">

<Extensions>

  <Extension Category="AppV.FileTypeAssociation">

    <FileTypeAssociation>

      <FileExtension MimeAssociation="true">

      <Name>.docm</Name>

      <ProgId>contosowordpad.DocumentMacroEnabled.12</ProgId>

      <PerceivedType>document</PerceivedType>

    <ContentType>application/vnd.ms-contosowordpad.document.macroEnabled.12</ContentType>

      <OpenWithList>

        <ApplicationName>wincontosowordpad.exe</ApplicationName>

      </OpenWithList>

     <OpenWithProgIds>

        <ProgId>contosowordpad.8</ProgId>

      </OpenWithProgIds>

      <ShellNew>

        <Command />

        <DataBinary />

        <DataText />

        <FileName />

        <NullFile>true</NullFile>

        <ItemName />

        <IconPath />

        <MenuText />

        <Handler />

      </ShellNew>

    </FileExtension>

    <ProgId>

       <Name>contosowordpad.DocumentMacroEnabled.12</Name>

      <DefaultIcon\>[{Windows}]\Installer\{90140000-0011-0000-0000-000000FF1CE}\contosowordpadicon.exe,15</DefaultIcon>

        <Description>Blah Blah Blah</Description>

        <FriendlyTypeName>[{FOLDERID_ProgramFilesX86}]\Microsoft Contoso 14\res.dll,9182</FriendlyTypeName>

        <InfoTip>[{FOLDERID_ProgramFilesX86}]\Microsoft Contoso 14\res.dll,1424</InfoTip>

        <EditFlags>0</EditFlags>

        <ShellCommands>

          <DefaultCommand>Open</DefaultCommand>

          <ShellCommand>

           <ApplicationId>{e56fa627-c35f-4a01-9e79-7d36aed8225a}</ApplicationId>

             <Name>Edit</Name>

             <FriendlyName>&Edit</FriendlyName>

           <CommandLine>"[{PackageRoot}]\Contoso\WINcontosowordpad.EXE" /vu "%1"</CommandLine>

          </ShellCommand>

          </ShellCommand>

          <ApplicationId>{e56fa627-c35f-4a01-9e79-7d36aed8225a}</ApplicationId>

            <Name>Open</Name>

            <FriendlyName>&Open</FriendlyName>

            <CommandLine>"[{PackageRoot}]\Contoso\WINcontosowordpad.EXE" /n "%1"</CommandLine>

            <DropTargetClassId />

            <DdeExec>

              <Application>mscontosowordpad</Application>

              <Topic>ShellSystem</Topic>

              <IfExec>[SHELLNOOP]</IfExec>

              <DdeCommand>[SetForeground][ShellNewDatabase"%1"]</DdeCommand>

            </DdeExec>

          </ShellCommand>

        </ShellCommands>

      </ProgId>

     </FileTypeAssociation>

   </Extension>

  </Extensions>

  </FileTypeAssociations>
```

**Url 通訊協定**擴展子系統會控制整合至用戶端電腦之本機登錄的 URL 協定，例如_mailto：_。 

```XML

<URLProtocols Enabled="true">

<Extensions>

<Extension Category="AppV.URLProtocol">

<URLProtocol>

  <Name>mailto</Name>

  <ApplicationURLProtocol>

  <DefaultIcon>[{ProgramFilesX86}]\MicrosoftContoso\Contoso\contosomail.EXE,-9403</DefaultIcon>

  <EditFlags>2</EditFlags>

  <Description />

  <AppUserModelId />

  <FriendlyTypeName />

  <InfoTip />

<SourceFilter />

  <ShellFolder />

  <WebNavigableCLSID />

  <ExplorerFlags>2</ExplorerFlags>

  <CLSID />

  <ShellCommands>

  <DefaultCommand>open</DefaultCommand>

  <ShellCommand>

  <ApplicationId>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationId>

  <Name>open</Name>

  <CommandLine>[{ProgramFilesX86}\Microsoft Contoso\Contoso\contosomail.EXE" -c OEP.Note /m "%1"</CommandLine>

  <DropTargetClassId />

  <FriendlyName />

  <Extended>0</Extended>

  <LegacyDisable>0</LegacyDisable>

  <SuppressionPolicy>2</SuppressionPolicy>

   <DdeExec>

  <NoActivateHandler />

  <Application>contosomail</Application>

  <Topic>ShellSystem</Topic>

  <IfExec>[SHELLNOOP]</IfExec>

  <DdeCommand>[SetForeground][ShellNewDatabase "%1"]</DdeCommand>

  </DdeExec>

  </ShellCommand>

  </ShellCommands>

  </ApplicationURLProtocol>

  </URLProtocol>

  </Extension>

  </Extension>

  </URLProtocols>
```

**軟體用戶端**擴充子系統可讓 app 以電子郵件用戶端、新聞閱讀程式、媒體播放機的形式登錄，並使應用程式在 [設定程式存取和電腦預設值] UI 中顯示。 在大多數情況下，您應該只需要啟用和停用。 如果您想讓其他用戶端（除了該用戶端除外），也可以使用此控制項來啟用和停用電子郵件用戶端。

```XML

<SoftwareClients Enabled="true">

  <ClientConfiguration EmailEnabled="false" />

</SoftwareClients>
```

**AppPaths**延伸子系統會開啟使用應用程式路徑註冊的 app。 例如，如果 contoso.exe 的 apppath 名稱是_myapp_，使用者可以在 [執行] 功能表中輸入_myapp_ ，並開啟 [contoso.exe]。

```XML

<AppPaths Enabled="true">

<Extensions>

<Extension Category="AppV.AppPath">

<AppPath>

  <ApplicationId>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationId>

  <Name>contosomail.exe</Name>

  <ApplicationPath>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationPath>

  <PATHEnvironmentVariablePrefix />

  <CanAcceptUrl>false</CanAcceptUrl>

  <SaveUrl />

</AppPath>

</Extension>

</Extensions>

</AppPaths>
```

**COM**擴展子系統可讓應用程式註冊到本機 COM 伺服器。 模式可以是：

-   結合
-   開 
-   關閉

```XML

<COM Mode="Isolated"/>
```

**虛擬核心物件**

```XML

<Objects Enabled="false" />
```

**虛擬**登錄在 HKCU 中設定虛擬機器碼。

```XML

<Registry Enabled="true">

<Include>

<Key Path="\REGISTRY\USER\[{AppVCurrentUserSID}]\Software\ABC">

<Value Type="REG_SZ" Name="Bar" Data="NewValue" />

 </Key>

  <Key Path="\REGISTRY\USER\[{AppVCurrentUserSID}]\Software\EmptyKey" />

 </Include>

<Delete>

</Registry>
```

**虛擬檔案系統**

```XML

    <FileSystem Enabled="true" />
```

**虛擬字型**

```XML

      <Fonts Enabled="false" />
```

**虛擬環境變數**

```XML

<EnvironmentVariables Enabled="true">

<Include>

       <Variable Name="UserPath" Value="%path%;%UserProfile%" />

       <Variable Name="UserLib" Value="%UserProfile%\ABC" />

       </Include>

      <Delete>

       <Variable Name="lib" />

        </Delete>

        </EnvironmentVariables>
```

**虛擬服務**

```XML

      <Services Enabled="false" />
```

#### UserScripts

使用 UserScripts 來設定或變更虛擬環境。  您也可以在部署時執行腳本，或在應用程式終止後清理環境。 若要查看範例腳本，請參閱排序器所產生的使用者設定檔。 下面的 [腳本] 區段提供了有關可使用的各種觸發程式的詳細資訊。

#### ManagingAuthority

在同一部電腦上共同存在套件的兩個版本時，請使用 ManagingAuthority，其中一個是部署到 app-v 4.6，另一個是在 App-v 5.0 上部署。 若要允許 App-v vNext 接管命名套件的 App-v 4.6 延伸點，請在 UserConfig 檔案中輸入下列內容（其中 PackageName 是 App-v 4.6 中的套件 GUID）：

```XML

<ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName="032630c0-b8e2-417c-acef-76fc5297fe81" />
```

## 部署設定檔（DeploymentConfig.xml）

DeploymentConfig 檔案提供電腦內容和使用者內容的配置設定，提供與 UserConfig 檔案中所列的相同功能。 當您將套件部署到執行 App-v 5.1 用戶端的電腦時，就會套用此設定。

使用 DeploymentConfig 檔案來指定或修改套件的自訂設定：

- 所有 UserConfig 設定
- 只能全域針對所有使用者套用的延伸
- 全域電腦位置的虛擬子系統，例如 registry
- 產品來源 URL
- 腳本（僅限電腦內容）
- 終止子進程的控制項

### 標頭

動態部署配置檔案的標頭如下所示：

```XML
<?xml version="1.0" encoding="utf-8"?><DeploymentConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/deploymentconfiguration">
```

**PackageId**的值與資訊清單檔案中的相同。

### Body

動態部署設定檔的主體包含兩個區段：

- **UserConfiguration：** 允許與前一節所述的使用者設定檔相同的內容。  將套件發佈給使用者時，本節中的任何 appextensions 設定設定都會覆寫套件內資訊清單中的對應設定，除非您提供使用者設定檔。 如果也提供 UserConfig 檔案，則會使用它，而不是部署設定檔中的使用者設定。 如果全域發佈套件，則只有部署設定檔的內容會與資訊清單搭配使用。 如需詳細資訊，請參閱[使用者設定檔內容（UserConfig.xml）](#user-configuration-file-contents-userconfigxml)。

- **MachineConfiguration：** 包含只能為整個電腦設定的資訊，不適用於電腦上的特定使用者。 例如，在 VFS 中 HKEY_LOCAL_MACHINE 登錄機碼。

```XML

<DeploymentConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/deploymentconfiguration">

<UserConfiguration>

...

</UserConfiguration>

<MachineConfiguration>

...

</MachineConfiguration>

...

</MachineConfiguration>

</DeploymentConfiguration>
```

### UserConfiguration

如需此區段所提供設定的詳細資訊，請參閱[使用者設定檔內容（UserConfig.xml）](#user-configuration-file-contents-userconfigxml) 。 

### MachineConfiguration

使用 [MachineConfiguration] 區段來設定整個電腦的資訊;不適用於電腦上的特定使用者。 例如，HKEY_LOCAL_MACHINE 虛擬機器中的登錄機碼。 這個元素中有四個小節可供使用：

1.  **[分系統](#subsystems-1)**
2.  **[ProductSourceURLOptOut](#productsourceurloptout)**
3.  **[MachineScripts](#machinescripts)**
4.  **[TerminateChildProcess](#terminatechildprocess)**

#### 分系統

AppExtensions 和其他子系統排列為子節點。

```XML

<MachineConfiguration>

  <Subsystems>

  …

  </Subsystems>

…

</MachineConfiguration>
```

您可以使用**Enabled**屬性來啟用或停用每個子系統。

**Extensions** 

某些子系統（延伸分系統）控制延伸。 子系統是預設程式所使用的應用程式功能。 針對這種類型的延伸，套件必須在全域發佈，以便整合到本機系統中。 同樣適用于使用者設定中之延伸的控制項和設定的規則也會套用至 MachineConfiguration 區段中的副檔名。

**應用程式功能**：由預設程式使用，允許應用程式將自己註冊為：

- 能夠開啟特定副檔名
- [開始] 功能表 internet 瀏覽器槽的 contender
- 能夠開啟特定的 windows MIME 類型

此延伸也會讓虛擬應用程式顯示在 [設定預設程式] UI 中。

```XML

<ApplicationCapabilities Enabled="true">

  <Extensions>

   <Extension Category="AppV.ApplicationCapabilities">

    <ApplicationCapabilities>


   <ApplicationId>[{PackageRoot}]\LitView\LitViewBrowser.exe</ApplicationId>

     <Reference>

      <Name>LitView Browser</Name>

      <Path>SOFTWARE\LitView\Browser\Capabilities</Path>

     </Reference>

   <CapabilityGroup>

    <Capabilities>


   <Name>@[{ProgramFilesX86}]\LitView\LitViewBrowser.exe,-12345</Name>


   <Description>@[{ProgramFilesX86}]\LitView\LitViewBrowser.exe,-12346</Description>

     <Hidden>0</Hidden>

     <EMailSoftwareClient>Lit View E-Mail Client</EMailSoftwareClient>

     <FileAssociationList>

      <FileAssociation Extension=".htm" ProgID="LitViewHTML" />

      <FileAssociation Extension=".html" ProgID="LitViewHTML" />

      <FileAssociation Extension=".shtml" ProgID="LitViewHTML" />

     </FileAssociationList>

     <MIMEAssociationList>

      <MIMEAssociation Type="audio/mp3" ProgID="LitViewHTML" />

      <MIMEAssociation Type="audio/mpeg" ProgID="LitViewHTML" />

     </MIMEAssociationList>

    <URLAssociationList>

      <URLAssociation Scheme="http" ProgID="LitViewHTML.URL.http" />

     </URLAssociationList>

     </Capabilities>

  </CapabilityGroup>

   </ApplicationCapabilities>

  </Extension>

</Extensions>

</ApplicationCapabilities>
```

_**支援的延伸子系統：**_ 

**電腦範圍的虛擬**登錄擴展子系統會在 HKEY_Local_Machine 的虛擬機器中設定登錄機碼。

```XML

<Registry>

<Include>

  <Key Path="\REGISTRY\\Machine\Software\ABC">

    <Value Type="REG_SZ" Name="Bar" Data="Baz" />

   </Key>

  <Key Path="\REGISTRY\Machine\Software\EmptyKey" />

 </Include>

<Delete>

</Registry>
```

**電腦範圍的虛擬核心物件**

```XML

<Objects>

<NotIsolate>

   <Object Name="testObject" />

 </NotIsolate>

</Objects>
```

#### ProductSourceURLOptOut

使用 ProductSourceURLOptOut 來指示套件的 URL 可透過_PackageSourceRoot_全域修改（以支援分支辦公室案例）。 變更會在下一次啟動時生效。 

```XML

<MachineConfiguration>

  ... 

  <ProductSourceURLOptOut Enabled="true" />

  ...

</MachineConfiguration>
```

#### MachineScripts

套件可以設定為在部署、發佈或移除時執行腳本。 若要查看範例腳本，請參閱排序器所產生的部署設定檔。 

下面的 [腳本] 區段提供了有關可使用的各種觸發程式的詳細資訊。

#### TerminateChildProcess

您可以指定應用程式可執行檔，其子進程會在應用程式 exe 進程終止時終止。

```XML

<MachineConfiguration>

  ...   

  <TerminateChildProcesses>

    <Application Path="[{PackageRoot}]\Contoso\ContosoApp.EXE" />

    <Application Path="[{PackageRoot}]\LitView\LitViewBrowser.exe" />

    <Application Path="[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE" />

  </TerminateChildProcesses>

  ...

</MachineConfiguration>
```



## 指令碼

下表說明各種腳本事件以及它們可以在其中執行的內容。

| 腳本執行時間       | 可在部署配置中指定 | 可在使用者配置中指定 | 可以在套件的虛擬環境中執行 | 可以在特定應用程式的內容中執行 | 在系統/使用者內容中執行：（部署設定、使用者配置） |
|-----------------------------|----------------------------------------------|----------------------------------------|---------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------------------------------|
| AddPackage                  | X                                            |                                        |                                                   |                                                     | （系統、不適用）                                                               |
| PublishPackage              | X                                            | X                                      |                                                   |                                                     | （系統、使用者）                                                              |
| UnpublishPackage            | X                                            | X                                      |                                                   |                                                     | （系統、使用者）                                                              |
| RemovePackage               | X                                            |                                        |                                                   |                                                     | （系統、不適用）                                                               |
| StartProcess                | X                                            | X                                      | X                                                 | X                                                   | （使用者、使用者）                                                                |
| ExitProcess                 | X                                            | X                                      |                                                   | X                                                   | （使用者、使用者）                                                                |
| StartVirtualEnvironment     | X                                            | X                                      | X                                                 |                                                     | （使用者、使用者）                                                                |
| TerminateVirtualEnvironment | X                                            | X                                      |                                                   |                                                     | （使用者、使用者）                                                                |

### 在單一事件觸發程式上使用多個腳本

App-v 5.1 支援在 App V 套件的單一事件觸發程式上使用多個腳本，包括您從 App-v 4.6 轉換到 App-v 5.0 或更新版本的套件。 若要啟用多個腳本的使用，App-v 5.1 使用名為 ScriptRunner.exe 的腳本啟動器應用程式，該應用程式是由應用程式 V 用戶端安裝的一部分所安裝。

### 如何在單一事件觸發程式上使用多個腳本

針對每個您想要執行的腳本，請將該腳本作為引數傳遞給 ScriptRunner.exe 應用程式。 然後，應用程式會分別執行每個腳本，以及您為每個腳本指定的引數。 每個觸發器只使用一個腳本（ScriptRunner.exe）。

> [!NOTE]
> 
> 我們建議您先從命令提示字元執行多腳本行，以確保所有引數都正確產生之後，才能將其新增至部署設定檔。

### 範例腳本與參數描述

使用下列範例檔案和資料表，修改部署或使用者設定檔，以新增您要執行的腳本。

```XML
<MachineScripts>
 <AddPackage>
   <Path>ScriptRunner.exe</Path>
   <Arguments>
   -appvscript script1.exe arg1 arg2 –appvscriptrunnerparameters –wait –timeout=10
   -appvscript script2.vbs arg1 arg2
   -appvscript script3.bat arg1 arg2 –appvscriptrunnerparameters –wait –timeout=30 –rollbackonerror
   </Arguments>
   <Wait timeout=”40” RollbackOnError=”true”/>
 </AddPackage>
</MachineScripts>
```


**範例檔案中的參數包括：**

#### \<AddPackage\>

您正在執行腳本的事件觸發程式名稱，例如新增套件或發佈套件。

#### \<Path\>ScriptRunner.exe\</Path\>

已安裝為 App-V 用戶端安裝之一部分的腳本啟動器應用程式。

> [!NOTE]
> 
> 雖然 ScriptRunner.exe 是作為 App-v 用戶端的一部分進行安裝，但是 App-v 用戶端的位置必須在% path% 中，否則 ScriptRunner 將無法執行。 ScriptRunner.exe 通常位於 C:FilesApplication Virtualizationfolder 中。

#### \<Arguments\>

`-appvscript` -代表您想要執行之實際腳本的權杖。

`script1.exe` –您想要執行的腳本名稱。

`arg1 arg2` –您想要執行之腳本的引數。

`-appvscriptrunnerparameters` –代表 script1.exe 執行選項的權杖。

`-wait` –權杖，通知 ScriptRunner 執行 script1.exe 完成，然後再繼續進行下一個腳本。

`-timeout=x` –在 x 秒數之後，通知 ScriptRunner 停止執行目前腳本的權杖。 所有其他指定的腳本仍會執行。

`-rollbackonerror` –權杖通知 ScriptRunner 停止執行所有尚未執行的腳本，並將錯誤回滾至 App-v 用戶端。

#### \<Wait timeout=”40” RollbackOnError=”true”/\>

等待 ScriptRunner.exe 的整體完成。

將 [整個流道] 的 [超時] 值設定為大於或等於個別腳本上超時值的總和。

如果有任何個別的腳本報告錯誤，且 rollbackonerror 已設定為 true，則 ScriptRunner 會將錯誤報表給 App-v 用戶端。

ScriptRunner 會執行任何檔案類型與電腦上已安裝的應用程式相關聯的任何腳本。 如果相關聯的應用程式遺失，或腳本的檔案類型沒有與電腦上的任何應用程式相關聯，則腳本不會執行。

### 使用 App-v 5.1 資訊清單檔案建立動態設定檔

您可以使用下列三種方法的其中一種來建立動態設定檔：手動、使用 App-v 5.1 管理主控台或對套件進行排序，這會產生兩個範例檔案。 如需如何使用 App-v 5.1 管理主控台建立檔案的詳細資訊，請參閱[如何使用 app-v 5.1 管理主控台來建立自訂的設定檔](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)。

若要手動建立檔案，前幾節中的資訊可以合併成單一檔案。 我們建議您使用排序器所產生的檔案。



- 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。
- 如果是 App-v 相關問題，請使用 app-v [TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題

- [如何使用 PowerShell 來套用部署設定檔案](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)

- [如何使用 PowerShell 來套用使用者設定檔案](how-to-apply-the-user-configuration-file-by-using-powershell51.md)

- [App-V 5.1 作業](operations-for-app-v-51.md)

---
