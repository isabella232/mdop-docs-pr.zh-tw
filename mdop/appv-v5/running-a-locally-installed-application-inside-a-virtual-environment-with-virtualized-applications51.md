---
title: 搭配虛擬化應用程式在虛擬環境內執行本機安裝的應用程式
description: 搭配虛擬化應用程式在虛擬環境內執行本機安裝的應用程式
author: dansimp
ms.assetid: 71baf193-a9e8-4ffa-aa7f-e0bffed2e4b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 384a1325b2f363595971f70f25fe0a25cade448d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800308"
---
# 搭配虛擬化應用程式在虛擬環境內執行本機安裝的應用程式


您可以在虛擬環境中執行本機安裝的應用程式，以及使用 Microsoft 應用程式虛擬化（App-v）虛擬化的應用程式。 如果您執行下列動作，您可能會想要這樣做：

-   想要在用戶端電腦上本機安裝並執行應用程式，但想要虛擬化並執行與該本機應用程式搭配使用的特定外掛程式。

-   正在針對 App-v 用戶端套件進行疑難排解，並想要在 App V 虛擬環境中開啟本機應用程式。

使用下列任何一種方法，在 App-v 虛擬環境內開啟本機應用程式：

-   [RunVirtual 登錄機碼](#bkmk-runvirtual-regkey)

-   [AppvClientPackage PowerShell Cmdlet](#bkmk-get-appvclientpackage-posh)

-   [命令列開關/appvpid： &lt; PID&gt;](#bkmk-cl-switch-appvpid)

-   [命令列掛鉤開關/appvve： &lt; GUID&gt;](#bkmk-cl-hook-switch-appvve)

每個方法實質上都是相同的工作，但是根據虛擬化應用程式是否已在執行中，某些方法可能比其他應用程式更適合一些。

## <a href="" id="bkmk-runvirtual-regkey"></a>RunVirtual 登錄機碼


若要將本機安裝的應用程式新增到套件或連線群組的虛擬環境中，您可以 `RunVirtual` 在 [登錄編輯程式] 中新增子機碼，如下列各節所述。

沒有可用來管理此登錄機碼的群組原則設定，因此您必須使用 System Center Configuration Manager 或其他電子軟體發佈（ESD）系統，或手動編輯註冊表。

### <a href="" id="bkmk-"></a>使用 RunVirtual 時的發佈套件支援的方法

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-V 版本</th>
<th align="left">支援的發佈方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3 和 App-v 5。1</p></td>
<td align="left"><p>全域發佈或供使用者使用</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 透過 App-v 5.0 SP2</p></td>
<td align="left"><p>僅限全域發佈</p></td>
</tr>
</tbody>
</table>

 

### 建立子機碼的步驟

1.  使用下表中的資訊，以可執行檔名稱（例如**MyApp.exe**）建立新的登錄機碼。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">套件發佈方法</th>
    <th align="left">建立登錄機碼的位置</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>全域發佈</p></td>
    <td align="left"><p>HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\RunVirtual</p>
    <p><strong>範例 </strong> ： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>發佈給使用者</p></td>
    <td align="left"><p>HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual</p>
    <p><strong>範例 </strong> ： HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>[連接] 群組可以包含：</p>
    <ul>
    <li><p>僅限全域發行或僅發佈給使用者的套件</p></li>
    <li><p>全域發佈及使用者的套件</p></li>
    </ul></td>
    <td align="left"><p>HKEY_LOCAL_MACHINE 或 HKEY_CURRENT_USER 金鑰，但下列所有專案都必須成立：</p>
    <ul>
    <li><p>如果您想要在虛擬環境中包含多個套件，您必須將它們包含在已啟用的連線群組中。</p></li>
    <li><p>針對連線群組中的其中一個套件，只建立一個子機碼。 例如，如果您有一個全域發佈的套件，以及另一個發佈給使用者的套件，您就會為其中一個套件建立子機碼，但不能同時為這兩者。 雖然您只為其中一個套件建立子機，但是連線群組中的所有套件，加上本機應用程式，都可在虛擬環境中使用。</p></li>
    <li><p>您要在其中建立子機碼的索引鍵必須符合您用於套件的發佈方法。</p>
    <p>例如，如果您已將套件發佈給使用者，您必須在下建立子機 <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code> 。</p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

     

2.  將新的登錄子機碼的值設定為套件的 PackageId 和 VersionId，並以底線分隔值。

    **語法**： &lt; PackageId &gt; \ _ &lt; VersionId&gt;

    **範例**： 4c909996-afc9-4352-b606-0b74542a09c1 \ _Be463724-Oct1-48f1-8604-c4bd7ca92fa

    上一個範例中的應用程式會產生如下所示的註冊表匯出檔案（.reg 檔案）：

    ``` syntax
    Windows Registry Editor Version 5.00 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual] 
    @="" 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe] 
    @="aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-555555555
    ```

## <a href="" id="bkmk-get-appvclientpackage-posh"></a>AppvClientPackage PowerShell Cmdlet


您可以使用**AppVVirtualProcess** Cmdlet 來檢索套件名稱，然後在指定套件的虛擬環境中啟動處理常式。 這個方法可讓您在 App-v 套件的內容中啟動任何命令，不論套件目前是否正在執行。

使用下列範例語法，並將套件的名稱取代為** &lt; 套件 &gt; **：

`$AppVName = Get-AppvClientPackage <Package>`

`Start-AppvVirtualProcess -AppvClientObject $AppVName cmd.exe`

如果您不知道套件的確切名稱，您可以使用命令列**AppvClientPackage \ * executable\\** <em> ，其中 **可執行檔 </em> *是應用程式的名稱，例如： AppvClientPackage \ * Word \ *。

## <a href="" id="bkmk-cl-switch-appvpid"></a>命令列開關/appvpid： &lt; PID&gt;


您可以將 **/appvpid： &lt; PID &gt; **開關套用到任何命令，讓您在選取的虛擬進程內執行該命令，方法是指定其進程識別碼（PID）。 使用這個方法會在與已執行的可執行檔相同的 App-v 環境中啟動新的可執行檔。

範例： `cmd.exe /appvpid:8108`

若要尋找 App-v 進程的進程識別碼（PID），請從提升許可權的命令提示字元執行命令**tasklist.exe** 。

## <a href="" id="bkmk-cl-hook-switch-appvve"></a>命令列掛鉤開關/appvve： &lt; GUID&gt;


這個選項可讓您在 App-v 套件的虛擬環境中執行本機命令。 與 **/appvid**切換（虛擬環境必須已執行）不同，此切換可讓您啟動虛擬環境。

句法 `cmd.exe /appvve:<PACKAGEGUID_VERSIONGUID>`

範例： `cmd.exe /appvve:aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-55555555`

若要取得應用程式的套件 GUID 與版本 GUID，請執行**AppvClientPackage** Cmdlet。 將 **/appvve**開關串連成下列：

-   冒號

-   所需套件的封裝 GUID

-   底線

-   所需套件的版本識別碼

如果您不知道套件的確切名稱，請使用命令列**AppvClientPackage \ * executable\\** <em> ，其中 **可執行檔 </em> *是應用程式的名稱，例如： AppvClientPackage \ * Word \ *。

這個方法可讓您在 App-v 套件的內容中啟動任何命令，不論套件目前是否正在執行。






## 相關主題


[App-V 5.1 技術參考資訊](technical-reference-for-app-v-51.md)

 

 





