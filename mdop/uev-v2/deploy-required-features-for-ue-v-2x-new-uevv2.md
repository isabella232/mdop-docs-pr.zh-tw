---
title: 部署 UE-V 2.x 的必要功能
description: 部署 UE-V 2.x 的必要功能
author: dansimp
ms.assetid: 10399bb3-cc7b-4578-bc0c-2f6b597abe4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2123ec75fb151a8f5b836b9b2522a9d6090b043
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810694"
---
# 部署 UE-V 2.x 的必要功能


所有 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 部署都需要這些功能

-   部署最終使用者可以存取的[設定儲存位置](#ssl)。

    這是一個儲存及檢索使用者設定的標準網路共用。

-   [選擇 UE-V 的配置方法](#config)

    UE-V 可以使用通用管理工具（包括群組原則、Configuration Manager 或 Windows 管理基礎結構和 Powershell）進行部署和設定。

-   部署要在同步處理設定的每台電腦上安裝的[Ue-v Agent](#agent) 。

    這會監視已註冊的應用程式與作業系統的任何設定變更，並在電腦之間同步處理這些設定。

本節中的主題描述如何部署這些功能。

## <a href="" id="ssl"></a>部署 UE-V 設定儲存位置


UE-V 需要在設定套件檔案中儲存使用者設定的位置。 您可以透過下列其中一種方式來設定儲存位置：

-   建立您自己的設定儲存位置

-   針對您的設定儲存位置使用現有的 Active Directory

如果您沒有建立設定儲存位置，UE-V Agent 預設會使用 Active Directory （AD）。

**注意**  
考慮[效能與容量規劃](https://technet.microsoft.com/library/dn458932.aspx#capacity)，並減少網路延遲的問題，請在使用者電腦所在的同一個本機網路上建立設定儲存位置。 針對設定儲存位置，我們建議每個使用者有 20 MB 的磁碟空間。



### 建立 UE-V 設定儲存位置

在您定義設定儲存位置之前，您必須先建立一個根目錄，並針對儲存在共用上設定的使用者提供讀/寫許可權。 UE-V Agent 會在這個根目錄下建立使用者專用的資料夾。

設定儲存位置是透過設定 [SettingsStoragePath 設定] 選項來定義，您可以使用下列其中一種方法加以設定：

-   當您透過命令列參數或在批次腳本中[部署 Ue-v Agent](#agent)時

-   透過[群組原則](https://technet.microsoft.com/library/dn458893.aspx)設定

-   使用[System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx)進行 ue-v

-   使用[Windows PowerShell 或 Windows 管理工具（WMI）](https://technet.microsoft.com/library/dn458937.aspx)安裝 ue-v Agent 之後

路徑必須位於伺服器和共用的通用命名慣例（UNC）路徑中。 例如， **\\\\Server\\Settingsshare\\**。 這個設定選項支援使用變數來啟用特定的同步處理案例。 例如，您可以使用變數， `%username%\%computername%` 在這些案例中保留使用者設定的體驗：

-   在企業中使用多個物理電腦的終端使用者

-   多名使用者使用的企業電腦

UE-V Agent 會根據 `SettingsPackages` **SettingsStoragePath**的設定設定，動態建立一個使用者專用的設定儲存路徑，並將隱藏的系統資料夾命名為。 代理程式會讀取並將設定寫入此位置，如已註冊的 UE-V 設定位置範本所定義。

**Ue-v 設定是由「上次寫入 wins」規則所決定：** 如果有多個受管理電腦的使用者的設定儲存位置相同，則一個 UE-V Agent 會讀取並寫入 [設定] 位置，而不是在其他電腦上執行的代理程式。 在下一個代理程式從設定儲存位置讀取時，會套用上次寫入的設定和值。

**部署設定儲存位置：** 請依照這些步驟來定義設定儲存位置，而不是使用您現有的 Active Directory 服務。 您應該將設定儲存空間共用的存取許可權制為需要它的使用者，如下表所示。

**部署 UE-V 網路共用**

1.  為 UE-V 使用者建立新的安全性群組。

2.  在集中位置的電腦上建立儲存 UE-V 設定套件的新資料夾，然後授與 UE-V 使用者存取資料夾的群組許可權。 支援 UE-V 的管理員必須擁有此共用資料夾的許可權。

3.  針對 [設定儲存位置] 資料夾設定下列共用層伺服器訊息區塊（SMB）許可權。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>使用者帳戶</strong></th>
    <th align="left"><strong>建議的許可權</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>沒有許可權</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 使用者的安全性群組</p></td>
    <td align="left"><p>完全控制</p></td>
    </tr>
    </tbody>
    </table>



4.  針對 [設定儲存位置] 資料夾設定下列 NTFS 檔案系統許可權。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>使用者帳戶</strong></th>
    <th align="left"><strong>建議的許可權</strong></th>
    <th align="left"><strong>資料夾</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>建立者/擁有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>僅限子資料夾和檔案</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 使用者的安全性群組</p></td>
    <td align="left"><p>列出資料夾/讀取資料、建立資料夾/附加資料</p></td>
    <td align="left"><p>僅限此資料夾</p></td>
    </tr>
    </tbody>
    </table>



使用此設定時，UE-V Agent 會在使用者的內容中執行時建立並保護 Settingspackage 資料夾，並授與每個使用者的許可權，以建立設定儲存空間的資料夾。 使用者在其 Settingspackage 資料夾中接收完全控制，而其他使用者則無法存取。

**注意**  
如果您在執行 Windows Server 作業系統的電腦上建立 [設定儲存空間共用]，請設定 UE-V，確認 [本機管理員] 群組或 [目前的使用者] 是儲存設定套件的資料夾擁有者。 若要啟用此額外的安全性，請在 Windows Server 登錄編輯程式中指定此設定：

1.  將名為 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**登錄機碼新增至**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**]。

2.  將 [登錄機碼] 值設定為*1*。



### 使用具有 UE-V 2 的 Active Directory。

如果沒有另行定義設定儲存位置，UE-V Agent 預設會使用 Active Directory （AD）。 在這些情況下，UE-V Agent 會動態地在每位使用者的 AD home directory 根目錄底下建立 [設定儲存空間] 資料夾。 但是，如果您在 AD 中設定自訂目錄設定，則會改為使用該目錄。

## <a href="" id="config"></a>選擇 UE-V 2 的配置方法。


您想要找出部署之後要用來管理 UE-V 的設定方法，因為這會是您用來部署 UE-V Agent 的設定方法。 通常，這是您在您的環境中已使用的配置方法，例如 Windows PowerShell 或 Configuration Manager。

您可以在 UE-V Agent 安裝之前、期間或之後設定 UE-V，視您使用的配置方法而定。

-   [群組原則](https://technet.microsoft.com/library/dn458893.aspx)**：** 您可以使用現有的群組原則基礎結構，在 ue-v agent 部署之前或之後設定 ue-v。 UE-V 群組原則 ADMX 範本可讓您集中管理通用的 UE-V Agent 設定選項，並且包括設定 UE-V 同步處理的設定。

    **安裝 Ue-v 群組原則 ADMX 範本：** UE-V 的群組原則 ADMX 範本設定 UE-V Agent 的同步處理設定，並使用現有的群組原則基礎結構啟用常見 UE-V Agent 設定設定的集中式管理。

    部署群組原則物件之網網域控制站支援的作業系統包括下列各項：

    Windows Server 2008 R2

    Windows Server 2012 和 Windows Server 2012 R2

-   [Configuration Manager](https://technet.microsoft.com/library/dn458917.aspx)**：** ue-v 設定套件可讓您使用 System Center configuration Manager 2012 SP1 或更新版本的相容性設定功能，在安裝了 ue-v 和 Configuration Manager 的各個網站上套用一致的設定。

-   [Windows powershell 和 WMI](https://technet.microsoft.com/library/dn458937.aspx)**：** 您可以在安裝 ue-v agent 之後，使用 windows powershell 和 windows Management Instrumentation （WMI）的指令碼命令來修改設定。

    **注意**  
    註冊表修改可能會造成資料遺失，或電腦變得不回應。 建議您使用其他配置方法。



-   **命令列或批次腳本安裝：**[部署 Ue-v Agent](#agent)時所使用的參數會設定許多 ue-v 設定。 電子軟體發佈系統，例如 System Center 2012 Configuration Manager，請在部署並安裝 UE-V Agent 軟體時，使用這些參數來設定用戶端。

## <a href="" id="agent"></a>部署 UE-V a.x 代理程式


UE-V Agent 是 UE-V 部署的核心，而且必須在使用 UE-V 的每台電腦上執行，才能同步處理應用程式和 Windows 設定。

**Ue-v Agent 安裝檔：** AgentSetup.exe 的單一安裝檔案，會在32位和64位作業系統上安裝 UE-V Agent。 此外，您也提供 AgentSetupx86.msi 或 AgentSetupx64.msi 架構特定的 Windows 安裝程式檔案，因為這些檔案較小，所以它們可能會簡化代理部署。 Windows 安裝程式安裝也支援[AgentSetup.exe 安裝程式的命令列參數](#params)。

**重要**  
在 UE-V Agent 安裝或卸載期間，您可以使用 AgentSetup.exe 檔案或 AgentSetup 的 &lt; &gt; .msi 檔案，但不能同時使用這兩個檔案。 必須使用相同的檔案才能卸載用來安裝 UE-V Agent 的 UE-V Agent。



### 部署 UE-V Agent

您可以使用下列方法來部署 UE-V Agent：

-   可安裝 Windows 安裝程式（.msi）檔案的電子軟體發佈（ESD）方案系統，例如建構管理員。

-   參照在共用中集中儲存的 Windows Installer （.msi）檔案的安裝腳本。

-   您在電腦上手動執行的安裝程式。

使用下列程式從網路共用部署 UE-V Agent。

**從網路共用安裝並設定 UE-V Agent**

1.  在使用者擁有 [讀取] 許可權的網路共用上，暫存 UE-V Agent 安裝檔 AgentSetup.exe。

2.  將腳本部署到安裝 UE-V Agent 的使用者電腦。 此腳本應指定設定儲存位置。

**部署選項：** 安裝 UE-V Agent 時，請務必使用正確的變數格式。 下表提供使用 AgentSetup.exe 或 Windows Installer （.msi）檔案之部署選項的範例。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>部署類型</strong></th>
<th align="left"><strong>部署描述</strong></th>
<th align="left"><strong>範例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>命令提示字元</p></td>
<td align="left"><p>當您在命令提示字元安裝 UE-V Agent 時，請使用 <em> % ^ username% </em> 變數格式。 如果由於設定儲存路徑中有空格而需要引號，請使用批次腳本檔案進行部署。</p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>批次處理腳本</p></td>
<td align="left"><p>當您從批次腳本檔案安裝 UE-V Agent 時，請使用 <em> %% username%% </em> 變數格式。 如果您使用這個安裝方法，您必須使用%% 字元來轉義變數。 如果沒有此字元，腳本會 <em> </em> 在安裝時（而不是在執行時間）展開使用者名稱變數，而不是在執行時間，這會讓 ue-v 針對所有使用者使用單一的設定儲存位置。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell</p></td>
<td align="left"><p>當您從 Windows PowerShell 提示或 Windows PowerShell 腳本安裝 UE-V Agent 時，請使用 <em> % username% </em> 變數格式。</p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>電子軟體發佈，例如部署 Configuration Manager 軟體部署</p></td>
<td align="left"><p>當您使用 Configuration Manager 安裝 UE-V Agent 時，請使用 <em> ^% username ^% </em> 變數格式。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>



**注意**  
UE-V Agent 的安裝需要系統管理員許可權，且電腦必須重新開機，才能執行 UE-V Agent。



### <a href="" id="params"></a>UE-V Agent 部署的命令列參數

UE-V Agent 的命令列參數如下所示。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>命令列參數</strong></th>
<th align="left"><strong>定義</strong></th>
<th align="left"><strong>附註</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/help 或/h 或/？</p></td>
<td align="left"><p>顯示 [AgentSetup.exe 用法] 對話方塊。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsStoragePath</p></td>
<td align="left"><p>指示定義儲存位置設定的通用命名慣例（UNC）路徑。</p></td>
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>您必須在 UE-V 2.1 和 UE-V 2.1 SP1 中指定 SettingsStoragePath。 您可以設定 AdHomePath 字串，以指定使用使用者&#39;s Active Directory 主路徑。 例如，<code>SettingsStoragePath = \share\path|AdHomePath</code>。</p>
<p>在 UE-V 2.0 中，您可以將 SettingsStoragePath 保留為空白，以改用 Active Directory 的主路徑。</p>
</div>
<div>

</div>
<p>已接受% username% 或% computername% 環境變數。 腳本可能需要轉義變數。</p>
<p><strong>預設值 </strong> ： &lt; 無&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SettingsStoragePathReg</p></td>
<td align="left"><p>在安裝期間從註冊表取得 SettingsStoragePath 值。</p></td>
<td align="left"><p>在命令提示字元中，輸入下列範例，強迫 UE-V 使用 Active Directory 主路徑，而不是特定的 UNC。</p>
<p><code>msiexec.exe /i AgentSetupx64.msi acceptlicenseterms=true SettingsStoragePathReg=TRUE /quiet /norestart</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsTemplateCatalogPath</p></td>
<td align="left"><p>表示通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。</p></td>
<td align="left"><p>只需要自訂設定位置範本</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RegisterMSTemplates</p></td>
<td align="left"><p>指定是否應在安裝期間註冊預設的 Microsoft 範本。</p></td>
<td align="left"><p>True |虛假</p>
<p><strong>預設值 </strong> ： True</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncMethod</p></td>
<td align="left"><p>指定應該使用哪一種同步處理方法。</p></td>
<td align="left"><p>SyncProvider |所有</p>
<p><strong>預設值 </strong> ： SyncProvider</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncTimeoutInMilliseconds</p></td>
<td align="left"><p>指定當它從設定儲存位置中檢索使用者設定時，電腦等待超時的毫秒數。</p></td>
<td align="left"><p><strong>預設值 </strong> ：2000毫秒</p>
<p>（等待最長2秒）</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncEnabled</p></td>
<td align="left"><p>指定是啟用還是停用 UE-V 同步處理。</p></td>
<td align="left"><p>True |虛假</p>
<p><strong>預設值 </strong> ： True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxPackageSizeInBytes</p></td>
<td align="left"><p>在 UE-V Agent 報告檔案超過閾值時，指定設定套件檔案大小（以位元組為單位）。</p></td>
<td align="left"><p>&lt;大小&gt;</p>
<p><strong>預設值 </strong> ：無（無警告閾值）</p></td>
</tr>
<tr class="even">
<td align="left"><p>CEIPEnabled</p></td>
<td align="left"><p>指定參與客戶經驗改進計畫的設定。 如果設為 <strong> True </strong> ，則會將安裝程式資訊上傳到 Microsoft 客戶經驗改進計畫網站。 如果設定為 <strong> False </strong> ，則不會上傳任何資訊。</p></td>
<td align="left"><p>True |虛假</p>
<p><strong>預設值 </strong> ： False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NoRestart</p></td>
<td align="left"><p>支援在安裝 UE-V Agent 之後延遲重新開機電腦。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>INSTALLFOLDER</p></td>
<td align="left"><p>啟用針對 UE-V Agent 或 UE-V 發生器設定不同的安裝資料夾。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>MUENABLED</p></td>
<td align="left"><p>讓安裝程式接受 Microsoft Update 程式中包含的選項。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ACCEPTLICENSETERMS</p></td>
<td align="left"><p>讓 UE-V 可以自行安裝。 必須將此屬性設為 <strong> True </strong> ，才能自行安裝 ue-v，並略過使用者接受 ue-v 授權條款的需求。 如果設定為 <strong> False </strong> 或保留空白，使用者就會收到錯誤訊息，而且沒有安裝 ue-v。</p></td>
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>此參數是自行安裝 UE-V 所必需的。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>NORESTART</p></td>
<td align="left"><p>在安裝 UE-V Agent 之後，避免強制重新開機。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### 更新 UE-V Agent

UE-V Agent 軟體的更新是透過 Microsoft Update 提供的。 您可以使用企業軟體發佈（ESD）基礎結構系統來部署 UE-V Agent 更新。

在 UE-V Agent 升級期間，您可以更新常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。

### 升級 UE-V a.x 代理程式

UE-V a.x Agent 會引進許多新功能，並修改代理程式將內容上傳到設定儲存空間共用的方式和時機。 升級程式會自動執行這些變更。 若要升級 UE-V Agent，請在使用者的電腦上執行 UE-V Agent 安裝套件（AgentSetup.exe、AgentSetupx86.msi 或 AgentSetupx64.msi）。

**注意**  
當您升級 UE-V Agent 時，您必須使用已安裝舊版 UE-V Agent 的相同安裝程式類型（.exe 檔案或 .msi 資料包）。 例如，使用 UE-V 2 AgentSetup.exe 升級使用 AgentSetup.exe 安裝的 UE-V 1.0 Agent。



當代理程式安裝程式執行時，會保留下列配置：

-   設定儲存路徑

-   登錄設定

-   排程的任務（間隔設定會重設為預設值）

**注意**  
在 UE-V 1.0 Agent 中註冊的 UE-V a.x 設定位置範本的電腦，會在 Windows 事件記錄檔中註冊錯誤。



您可以使用 Microsoft System Center 2012 Configuration Manager 或其他企業軟體發佈工具來自動化並散佈 UE-V Agent 升級。

**建議：** 我們建議您升級計算環境中的所有 UE-V 1.0 Agent，但這不是必要的。 UE-V a.x 設定位置範本可以與 UE-V 1.0 Agent 互動，因為它們只會共用設定儲存路徑中的設定。 不過，我們建議您將部署移至單一的代理程式版本，以簡化管理並支援 UE-V。

### 升級失敗之後，請修復 UE-V Agent

嘗試下列其中一項操作後，您可能會遇到錯誤：

-   從 UE-V 1.0 升級到 UE-V 2

-   升級至較新版本的 Windows，例如從 Windows 7 移至 Windows 8 或從 Windows 8 升級至 Windows 8.1。

-   升級 UE-V Agent 之後卸載代理程式

若要解決任何問題，請嘗試在安裝代理程式的電腦上的命令提示字元中輸入這個命令來修復 UE-V Agent。

``` syntax
msiexec.exe /f "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log
```

然後，您可以安裝較新版的 UE-V Agent 來重試卸載程式或升級。






## 相關主題


[準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[部署自訂應用程式的 UE-V 2. x](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)









