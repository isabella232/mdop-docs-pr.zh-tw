---
title: 關於 App-V 5.0 SP3
description: 關於 App-V 5.0 SP3
author: dansimp
ms.assetid: 67b5268b-edc1-4027-98b0-b3937dd70a6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: bc72f3f72c2b06470287dfe4ba3ed22abcc6068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800726"
---
# 關於 App-V 5.0 SP3


使用下列各節，查看適用于 Microsoft Application Virtualization （App-v） 5.0 SP3 的重大變更資訊：

-   [App-V 5.0 SP3 軟體先決條件及支援的設定](#bkmk-sp3-prereq-configs)

-   [遷移至 App-v 5.0 SP3](#bkmk-migrate-to-50sp3)

-   [手動建立的連線群組 xml 檔案需要更新至架構](#bkmk-update-schema-cg)

-   [連線群組的改良功能](#bkmk-cg-improvements)

-   [系統管理員可以發佈及取消發佈特定使用者的套件](#bkmk-usersid-pub-pkgs-specf-user)

-   [僅允許系統管理員發佈及取消發佈套件](#bkmk-admins-only-pub-unpub-pkgs)

-   [RunVirtual 登錄機碼支援發佈給使用者的套件](#bkmk-runvirtual-reg-key)

-   [新的 PowerShell Cmdlet 及可更新的 Cmdlet 說明](#bkmk-posh-cmdlets-help)

-   [主要虛擬應用程式目錄（PVAD）已隱藏，但可以開啟](#bkmk-pvad-hidden)

-   [需要 ClientVersion，才能查看 App-v 發佈中繼資料](#bkmk-pub-metadata-clientversion)

-   [App-v 事件記錄已合併](#bkmk-event-logs-moved)

## <a href="" id="bkmk-sp3-prereq-configs"></a>App-V 5.0 SP3 軟體先決條件及支援的設定


請參閱 App-V 5.0 SP3 軟體必備元件及支援的設定的下列連結。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">連結至先決條件和支援的設定</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-50-sp3-prerequisites.md" data-raw-source="[App-V 5.0 SP3 Prerequisites](app-v-50-sp3-prerequisites.md)">App-V 5.0 SP3 必要條件</a></p></td>
<td align="left"><p>在啟動 App-v 5.0 SP3 安裝之前必須安裝的必備軟體</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 支援的組態</a></p></td>
<td align="left"><p>支援的作業系統與 App-v Server、Sequencer 及用戶端元件的硬體需求</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-migrate-to-50sp3"></a>遷移至 App-v 5.0 SP3


使用下列資訊升級到舊版的 App-v 5.0 SP3。

### 開始升級前

在您開始升級前，請先查看下列資訊：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">升級前要檢查的專案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要升級的元件</p></td>
<td align="left"><ol>
<li><p>App-v Server</p></li>
<li><p>Midi</p></li>
<li><p>App-V 用戶端或 App-v 遠端桌面服務（RDS）用戶端</p></li>
<li><p>連線群組</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>若要使用應用程式-V 用戶端使用者介面，請從 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Microsoft Application Virtualization 5.0 用戶端 UI 應用程式下載現有版本 </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>從 App-v （V）升級</p></td>
<td align="left"><p>您必須先升級到 App-v 5.0。 您無法直接從 App-v （即 app-v）升級到 App-v 5.0 SP3。</p>
<p>如需詳細資訊，請參閱：</p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">關於 App-V 5.0</a> </p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)">規劃從舊版 App-V 移轉</a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>從 App-v 5.0 或更新版本升級</p></td>
<td align="left"><p>您可以直接從下列任何一個版本升級到 app-v 5.0 SP3：</p>
<ul>
<li><p>App-V 5。0</p></li>
<li><p>App-V 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul>
<p>若要升級至 App-v 5.0 SP3，請按照本文其餘章節中的步驟進行。</p></td>
</tr>
<tr class="even">
<td align="left"><p>升級後對套件和連線群組所需的變更</p></td>
<td align="left"><p>無。 套件和連線群組會像目前一樣繼續運作。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a>升級 App-v 基礎結構的步驟

完成下列步驟，將 App-v 基礎結構的每個元件升級至 App-v 5.0 SP3。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>步驟1：升級 App-v 伺服器。</p>
<p>如果您不是使用 App-v Server，請跳過這個步驟，然後移至下一個步驟。</p>
<div class="alert">
<strong>注意</strong><br/><p>App-V 5.0 SP3 用戶端與 App-v 5.0 SP1 Server 相容。</p>
</div>
<div>

</div></td>
<td align="left"><p>請依照下列步驟執行：</p>
<ol>
<li><p>請參閱 <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)"> app-v 5.0 SP3 的版本資訊， </a> 以瞭解可能會影響 App V 伺服器安裝的問題。</p></li>
<li><p>視您用來升級管理資料庫和/或報告資料庫的方法而定，請執行下列其中一項操作：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">資料庫升級方法</th>
<th align="left">步驟</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Installer</p></td>
<td align="left"><p>跳過這個步驟，移至步驟3： [如果您要升級 App-v Server ...]</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL 腳本</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>管理資料庫</strong></p></td>
<td align="left"><p>若要安裝或升級，請參閱 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安裝或升級 app-v 5.0 SP3 管理伺服器資料庫失敗的 SQL 腳本 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>報表資料庫</strong></p></td>
<td align="left"><p>依照 <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)"> 如何使用 SQL 腳本部署 App-v 資料庫的步驟進行 </a> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>
<p> </p></li>
<li><p>如果您要從 App-v 5.0 SP1 修復程式套件3或更新版本升級 app-v Server，請完成 <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)"> 安裝 app-v 5.0 SP3 Server 後檢查登錄機碼一節中的步驟 </a> 。</p></li>
<li><p>遵循 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> 如何部署 app-v 5.0 Server 的步驟進行 </a> 。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>步驟2：升級 App-v 排序器。</p></td>
<td align="left"><p>瞭解 <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"> 如何安裝排序器 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>步驟3：升級 App-v 用戶端或 App-v RDS 用戶端。</p></td>
<td align="left"><p>瞭解 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> 如何部署 App-v 用戶端 </a> 。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-check-reg-key-svr"></a>安裝 App-v 5.0 SP3 Server 之前檢查登錄機碼

這是上表中的步驟3。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>需要此步驟時</strong></p></td>
<td align="left"><p>您要從 App-v SP1 升級到您使用 .msp 檔案安裝的任何後續修復程式套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>哪些元件需要您執行此步驟</strong></p></td>
<td align="left"><p>僅限您要升級的 App-v Server 元件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>當您需要執行此步驟時</strong></p></td>
<td align="left"><p>將 App-v Server 升級至 App-v 5.0 SP3 之前</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>您需要執行的動作</strong></p></td>
<td align="left"><p>使用下清單格中的資訊， <code>HKLM\Software\Microsoft\AppV\Server</code> 以您在原始伺服器安裝中所提供的值來更新每個登錄項的值。 完成此步驟會還原在安裝 App-v SP1 修復程式套件時可能已移除的註冊表值。</p></td>
</tr>
</tbody>
</table>



**ManagementDatabase 鍵**

如果您要安裝管理資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>說明是否需要公用存取帳戶才能存取非本地管理資料庫。 如果需要，值會設定為 "1"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_NAME</p></td>
<td align="left"><p>管理資料庫的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用於讀取（公開）管理資料庫存取權的帳戶。</p>
<p>在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用來讀取（公開）管理資料庫存取權的帳戶的安全識別碼（SID）。</p>
<p>在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理資料庫的 SQL Server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用於寫入管理資料庫（系統管理員）存取權的帳戶。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用來撰寫（系統管理員）存取管理資料庫之帳戶的安全識別碼（SID）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>管理伺服器遠端電腦帳戶（[域 \ 帳戶]）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>管理伺服器（域 \ 帳戶）的安裝管理員登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有效值如下：</p>
<ul>
<li><p><strong>1 </strong> -此管理服務是在本機電腦上，也就是 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 是空白的。</p></li>
<li><p><strong>0 </strong> - 管理服務與本機電腦位於不同的電腦上。</p></li>
</ul></td>
</tr>
</tbody>
</table>



**ManagementService 鍵**

如果您要安裝管理伺服器，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MANAGEMENT_ADMINACCOUNT</p></td>
<td align="left"><p>已授權管理 App-v （網域 \ 帳戶）的 Active Directory 網域服務（AD DS）群組或帳戶。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>包含管理資料庫的 SQL server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>包含管理資料庫的遠端 SQL 伺服器名稱。</p>
<p>如果此值為空白，則會使用本機電腦。</p></td>
</tr>
</tbody>
</table>



**ReportingDatabase 鍵**

如果您要安裝報告資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>說明存取非本地報告資料庫是否需要公用存取帳戶。 如果需要，值會設定為 "1"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_NAME</p></td>
<td align="left"><p>報告資料庫的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用於讀取（公開）存取報表資料庫的帳戶。</p>
<p>在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>帳戶的安全識別碼（SID），用於讀取（公開）的報表資料庫存取權。</p>
<p>在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>報表資料庫的 SQL Server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>報表伺服器遠端電腦帳戶（[域 \ 帳戶]）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>報表服務器（域 \ 帳戶）的安裝管理員登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有效值如下：</p>
<ul>
<li><p><strong>1 </strong> -報表服務位於本機電腦上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 為空白。</p></li>
<li><p><strong>0 </strong> - 報表服務與本機電腦在不同的電腦上。</p></li>
</ul></td>
</tr>
</tbody>
</table>



**ReportingService 鍵**

如果您要安裝報表伺服器，請在中設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>報表資料庫的 SQL Server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>具有報告資料庫之遠端 SQL 伺服器的名稱。</p>
<p>如果此值為空白，則會使用本機電腦。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-update-schema-cg"></a>手動建立的連線群組 xml 檔案需要更新至架構


如果您要手動建立連線群組 XML 檔案，且想要使用新的「選用套件」和「使用任何版本」功能（在連線群組的[改善](#bkmk-cg-improvements)中所述），您必須在 XML 檔案中指定下列架構：

`xmlns="http://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"`

如需範例及詳細資訊，請參閱[關於連線群組](about-the-connection-group-file.md)檔案。

## <a href="" id="bkmk-cg-improvements"></a>連線群組的改良功能


您可以使用應用程式 V 5.0 SP3 中新增的選用套件和其他改進，更輕鬆地管理連線群組。 下表摘要列出您可以使用新的連線群組功能執行的工作，以及每個任務的詳細資訊連結。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務/功能</th>
<th align="left">描述</th>
<th align="left">詳細資訊的連結</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>讓連線群組包含選用套件</p></td>
<td align="left"><p>在連線群組中包含選用套件，可讓您動態判斷哪些應用程式將包含在連線群組的虛擬環境中（根據使用者有資格使用的應用程式而定）。</p>
<p>您不需要管理多個連線群組，因為您可以在同一個連接群組中混合選用和非選用的套件。 混合套件可讓不同的使用者群組使用相同的連線群組，即使使用者可能只有一個相同的套件也一樣。</p>
<p><strong>範例 </strong> ：您可以在 Microsoft Office 中為所有使用者啟用套件，但啟用不同的選擇性套件（包含不同的 Office 外掛程式）至不同的使用者子集。</p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">如何在連線群組中使用選用套件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>取消發佈或刪除選用的套件，而不變更連接群組</p></td>
<td align="left"><p>取消發佈或刪除或取消發佈並重新發佈在連線群組中的選擇性套件，而不需要停用或重新啟用 App-v 用戶端的連線群組。</p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">如何在連線群組中使用選用套件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>發佈包含使用者發佈及全域發佈套件的連線群組</p></td>
<td align="left"><p>建立使用者發佈的連線群組，其中包含使用者發佈及全域發佈的套件。</p></td>
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)">如何以使用者發佈的套件與全域發佈的套件建立連線群組</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>建立連線群組以忽略套件版本</p></td>
<td align="left"><p>將連線群組設定為接受任何版本的套件，這可讓您在不需停用連接群組的情況下升級套件。 此外，如果有選擇性套件的 [連線] 群組中有不正確的版本，套件會被忽略，而且不會封鎖連線群組的虛擬環境。</p></td>
<td align="left"><p><a href="how-to-make-a-connection-group-ignore-the-package-version.md" data-raw-source="[How to Make a Connection Group Ignore the Package Version](how-to-make-a-connection-group-ignore-the-package-version.md)">如何讓連線群組略過套件版本</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>限制最終使用者的發佈功能</p></td>
<td align="left"><p>僅允許系統管理員（而非最終使用者）發佈套件及啟用連線群組。</p></td>
<td align="left"><p>如需連線群組的相關資訊，請參閱 <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)"> 如何只允許系統管理員啟用連線群組</a></p>
<p>如需套件的相關資訊，請參閱下列文章：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">連結至詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理主控台</p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)">如何使用 Management Console 發佈套件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)">如何使用 PowerShell 來管理獨立電腦上的連線群組</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>協力廠商電子軟體傳遞系統</p></td>
<td align="left"><p><a href="how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md" data-raw-source="[How to Enable Only Administrators to Publish Packages by Using an ESD](how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md)">如何只讓系統管理員使用 ESD 來發佈套件</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>啟用或停用特定使用者的連線群組</p></td>
<td align="left"><p>系統管理員可以使用 optional <strong> （UserSID） </strong> 參數與下列 Cmdlet 來啟用或停用特定使用者的連線群組：</p>
<ul>
<li><p>Enable-AppVClientConnectionGroup</p></li>
<li><p>Disable-AppVClientConnectionGroup</p></li>
</ul></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic)">如何使用 PowerShell 來管理獨立電腦上的連線群組</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>將相同的套件路徑合併成連接群組中的一個虛擬目錄</p></td>
<td align="left"><p>如果連線群組中有兩個以上的套件包含完全相同的目錄路徑，則會將這些路徑合併到連線群組虛擬環境內的單一虛擬目錄中。</p>
<p>這種路徑合併可讓一個套件中的應用程式存取不同套件中的檔案。</p></td>
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp)">關於連線群組虛擬環境</a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-usersid-pub-pkgs-specf-user"></a>系統管理員可以發佈及取消發佈特定使用者的套件


系統管理員可以使用下列 Cmdlet 來發佈或取消發佈特定使用者的套件。 若要使用 Cmdlet，請輸入 **-UserSID**參數，後面接著使用者的安全性識別碼（SID）。 如需詳細資訊，請參閱：

-   [如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-pub-pkg-a-user-standalone-posh)

-   [如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-unpub-pkg-specfc-use)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Cmdlet</th>
<th align="left">範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>發佈-AppvClientPackage</p></td>
<td align="left"><p>發佈-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
</tr>
<tr class="even">
<td align="left"><p>取消發佈-AppvClientPackage</p></td>
<td align="left"><p>取消發佈-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-admins-only-pub-unpub-pkgs"></a>僅允許系統管理員發佈及取消發佈套件


您可以使用下列其中一種方法，僅啟用系統管理員（而非最終使用者）來發佈及取消發佈套件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>群組原則設定</p></td>
<td align="left"><p>流覽至下列群群組原則物件節點：</p>
<p><strong>[電腦設定 &gt; 原則] &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈 </strong> 。</p>
<p>啟用 [ <strong> 需要發佈為系統管理員] </strong> 群群組原則設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-runvirtual-reg-key"></a>RunVirtual 登錄機碼支援發佈給使用者的套件


App-v 5.0 SP3 新增了對使用**RunVirtual**登錄機碼與使用者發佈套件中的虛擬化應用程式的支援。 **RunVirtual**登錄機碼可讓您在虛擬環境中執行本機安裝的應用程式，以及使用 app-v 已虛擬化的應用程式。

之前，App-v 中的虛擬化應用程式必須全域發佈。 如需更多關於**RunVirtual**和其他在虛擬環境中使用虛擬化應用程式執行本機安裝應用程式的方法，請參閱[使用虛擬化應用程式在虛擬環境中執行本機安裝的應用程式](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)。

## <a href="" id="bkmk-posh-cmdlets-help"></a>新的 PowerShell Cmdlet 及可更新的 Cmdlet 說明


App-V 5.0 SP3 中包含新的 PowerShell Cmdlet 及可更新的 Cmdlet 說明。 若要下載 Cmdlet 模組，請參閱[如何載入 PowerShell Cmdlet 及取得 Cmdlet](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets)說明。

### 新的 App-V 5.0 SP3 Server PowerShell Cmdlet

已新增適用于 App-v Server 的新 Windows PowerShell Cmdlet，以協助您管理連線群組。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Cmdlet</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>附加 AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>將套件附加到連線群組的結尾&#39;s 套件清單，並讓您將套件設定為選用，且在連線群組中不使用任何版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Set-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>可讓您編輯連線群組套件的詳細資料，例如，是否選用此選項。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>移除-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>從連線群組中移除套件。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-get-cmdlet-help"></a>取得 PowerShell Cmdlet 的說明

以下格式提供 Cmdlet 說明：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">格式</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以可下載的模組</p></td>
<td align="left"><p>若要在下載 Cmdlet 模組之後取得最新的協助：</p>
<ol>
<li><p>開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</p></li>
<li><p>輸入下列其中一個命令來載入您想要的模組的 Cmdlet：</p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 元件</th>
<th align="left">輸入的命令</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server</p></td>
<td align="left"><p>更新-協助-模組 AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>更新-協助-模組 AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 用戶端</p></td>
<td align="left"><p>更新-協助-模組 AppvClient</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上為網頁</p></td>
<td align="left"><p>請參閱 Microsoft 桌上出版 [優化套件自動化] 下的 app-v 節點， <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> 以使用 Windows PowerShell </a> 。</p></td>
</tr>
</tbody>
</table>



如需詳細資訊，請參閱[如何載入 PowerShell Cmdlet 及取得 Cmdlet](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)說明。

## <a href="" id="bkmk-pvad-hidden"></a>主要虛擬應用程式目錄（PVAD）已隱藏，但可以開啟


主虛擬應用程式目錄（PVAD）在 App-v 5.0 SP3 中是隱藏的，但您可以重新開啟它，並使用下列其中一種方法讓它可見：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步驟</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用命令列參數</p></td>
<td align="left"><p>將 <strong> – EnablePVADControl </strong> 參數傳遞到 <strong>Sequencer.exe</strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>建立登錄子機碼</p></td>
<td align="left"><ol>
<li><p>在 [登錄編輯程式] 中，流覽至： <code>HKLM\SOFTWARE\Microsoft\AppV\Sequencer\Compatibility</code></p>
<div class="alert">
<strong>注意</strong><br/><p>如果 <code>Compatibility</code> 該子機不存在，您就必須建立它。</p>
</div>
<div>

</div></li>
<li><p>建立名為 EnablePVADControl 的 DWORD 值 <strong> </strong> ，並將該值設定為 <strong> 1 </strong> 。</p>
<p>值為 <strong> 0 </strong> 表示 PVAD 已隱藏。</p></li>
</ol></td>
</tr>
</tbody>
</table>



**更多關於 PVAD 的資訊：** 當您使用 Sequencer 建立套件時，您可以輸入套件的任何安裝路徑。 在過去的 App-v 版本中，您必須指定應用程式的主要虛擬應用程式目錄（PVAD）作為路徑。 PVAD 是您通常在本機電腦上安裝應用程式的目錄（如果您使用的是 App-v）。 例如，如果您在電腦上安裝 Office，則 PVAD 通常會 C:\\program files Files\\Microsoft Office\\。

## <a href="" id="bkmk-pub-metadata-clientversion"></a>需要 ClientVersion，才能查看 App-v 發佈中繼資料


在 App-V 5.0 SP3 中，當您查詢 app-v 發佈伺服器以取得中繼資料時，您必須在位址中提供下列值：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">其他詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ClientVersion</strong></p></td>
<td align="left"><p>如果您省略 <strong> 查詢的 ClientVersion </strong> 參數，中繼資料會排除新的 APP-V 5.0 SP3 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ClientOS</strong></p></td>
<td align="left"><p>您必須在順序套件時選取特定用戶端作業系統，才能提供這個值。 如果您選取 [預設（所有作業系統）]，請勿在查詢中指定這個值。</p>
<p>如果您在查詢中省略 <strong> ClientOS </strong> 參數，則只有已排序支援任何作業系統的套件才會出現在中繼資料中。</p></td>
</tr>
</tbody>
</table>



如需此查詢的語法及範例，請參閱[查看 App-v Server 發佈中繼資料](viewing-app-v-server-publishing-metadata.md)。

## <a href="" id="bkmk-event-logs-moved"></a>App-v 事件記錄已合併


已將下列事件記錄（先前位於**應用程式和服務記錄/microsoft/appv/ &lt; app-v 元件 &gt; **）移至**應用程式和服務記錄/microsoft/appv/ServiceLog**。

若要查看記錄，請**選取** &gt; [事件檢視器] 應用程式中的 [**顯示分析記錄及調試記錄**]。

用戶端-目錄用戶端整合用戶端-Orchestration 用戶端-PackageConfig 用戶端-腳本用戶端-服務用戶端-Vemgr 用戶端-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary 子系統-ActiveX 子系統-AppPath 子系統-Com 子系統-fta

## 如何取得 MDOP 技術


App-v 是 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049)。






## 相關主題


[App-V 5.0 SP3 版本資訊](release-notes-for-app-v-50-sp3.md)









