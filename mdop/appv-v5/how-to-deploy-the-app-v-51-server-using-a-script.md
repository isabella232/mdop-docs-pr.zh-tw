---
title: 如何使用指令碼來部署 App-V 5.1 伺服器
description: 如何使用指令碼來部署 App-V 5.1 伺服器
author: dansimp
ms.assetid: 15c33d7b-9b61-4dbc-8674-399bb33e5f7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/20/2020
ms.openlocfilehash: 579ca685f677aaaa4f5ebb6ac8d2969fdcbe2cd2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800516"
---
# 如何使用指令碼來部署 App-V 5.1 伺服器

若要使用命令列成功完成**appv\_server\_setup.exe**伺服器設定，您必須指定併合並多個參數。

## 使用腳本安裝 App-V 5.1 伺服器

- 使用命令列來安裝 App-V 5.1 伺服器的下列資訊。

    > [!NOTE]
    > 您也可以使用命令列來存取下清單格中的資訊，方法是輸入以下命令： **appv\_server\_setup.exe/？**。

### 在本機電腦上安裝管理伺服器與管理資料庫

下列參數對於 Microsoft SQL Server 的預設與自訂實例都是有效的：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /DB_PREDEPLOY_MANAGEMENT
- /MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT
- /MANAGEMENT_DB_NAME

**範例：使用 Microsoft SQL Server 的自訂實例**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement"
```

### 在本機電腦上使用現有的管理資料庫來安裝管理伺服器

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_MANAGEMENT_DB_NAME

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /EXISTING_MANAGEMENT_DB_NAME

**範例：使用 Microsoft SQL Server 的自訂實例**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### 在遠端電腦上使用現有的管理資料庫來安裝管理伺服器

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_MANAGEMENT_DB_NAME

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /EXISTING_MANAGEMENT_DB_NAME

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME="SqlServermachine.domainName" /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### 在同一部電腦上安裝管理資料庫和管理伺服器

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_SERVER_MACHINE_USE_LOCAL
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_SERVER_MACHINE_USE_LOCAL
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

**範例：使用 Microsoft SQL Server 的自訂實例**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_SERVER_MACHINE_USE_LOCAL /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 在與管理伺服器不同的電腦上安裝管理資料庫

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

**範例：使用 Microsoft SQL Server 的自訂實例**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 安裝發佈伺服器

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：

- /PUBLISHING_SERVER
- /PUBLISHING_MGT_SERVER
- /PUBLISHING_WEBSITE_NAME
- /PUBLISHING_WEBSITE_PORT

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
appv_server_setup.exe /QUIET /PUBLISHING_SERVER /PUBLISHING_MGT_SERVER="http://ManagementServerName:ManagementPort" /PUBLISHING_WEBSITE_NAME="Microsoft AppV Publishing Service" /PUBLISHING_WEBSITE_PORT="8081"
```

### 在本機電腦上安裝報表伺服器與報告資料庫

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /REPORTING _SERVER
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /REPORTING _DB_NAME

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /REPORTING _SERVER
- */REPORTING _ADMINACCOUNT*
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_CUSTOM_SQLINSTANCE*
- /REPORTING _DB_NAME

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting"
```

### 在本機電腦上安裝報表伺服器並使用現有的報表資料庫

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /REPORTING _SERVER
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_REPORTING _DB_NAME

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /REPORTING _SERVER
- */REPORTING _ADMINACCOUNT*
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE*
- /EXISTING_REPORTING _DB_NAME

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### 在遠端電腦上使用現有的報表資料庫來安裝報表伺服器

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /REPORTING _SERVER
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_REPORTING _DB_NAME

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /REPORTING _SERVER
- */REPORTING _ADMINACCOUNT*
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE*
- /EXISTING_REPORTING _DB_NAME

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME="SqlServerMachine.DomainName" /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### 在報表伺服器所在的電腦上安裝報表資料庫

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /REPORTING _DB_NAME
- /REPORTING_SERVER_MACHINE_USE_LOCAL
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_CUSTOM_SQLINSTANCE*
- /REPORTING _DB_NAME
- /REPORTING_SERVER_MACHINE_USE_LOCAL
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_SERVER_MACHINE_USE_LOCAL /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 在不同的電腦上安裝報表資料庫，而不是報表伺服器

若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：

- /DB_PREDEPLOY_REPORTING
- /REPORTING _DB_SQLINSTANCE_USE_DEFAULT
- /REPORTING _DB_NAME
- /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：

- /DB_PREDEPLOY_REPORTING
- /REPORTING _DB_CUSTOM_SQLINSTANCE
- /REPORTING _DB_NAME
- /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

**範例：使用 Microsoft SQL Server 的自訂實例：**

```dos
 appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 參數定義

#### 一般參數

| 參數 | 資訊 |
|--|--|
| /QUIET | 指定 [緘默安裝]。 |
| /UNINSTALL | 指定卸載。 |
| /LAYOUT | 指定 [版面配置] 動作。 這會將 MSIs 和腳本檔案解壓縮至資料夾，而不會實際安裝產品。 不需要任何值。 |
| /LAYOUTDIR | 指定版面配置目錄。 接受字串。 範例用法： **/LAYOUTDIR = "C:\\Application Virtualization 伺服器"** |
| /INSTALLDIR | 指定安裝目錄。 接受字串。 範例用法： **/INSTALLDIR = "C:\\program files Files\\Application Virtualization\\Server"** |
| /MUOPTIN | 啟用 Microsoft Update。 不需要任何值。 |
| /ACCEPTEULA | 接受授權合約。 這對於無操作安裝是必要的。 範例用法： **/ACCEPTEULA**或 **/ACCEPTEULA = 1** |

#### 管理伺服器安裝參數

|參數 |資訊 |
|--|--|
| /MANAGEMENT_SERVER | 指定將安裝管理伺服器。 不需要任何值 |
| /MANAGEMENT_ADMINACCOUNT | 指定允許系統管理員存取管理伺服器的帳戶。 這可以是使用者帳戶或群組。 範例用法： **/MANAGEMENT_ADMINACCOUNT = "mydomain\\admin"**。 如果未指定 **/MANAGEMENT_SERVER** ，將會忽略此情況。 |
| /MANAGEMENT_WEBSITE_NAME | 指定將為管理服務建立的網站名稱。 範例用法： **/MANAGEMENT_WEBSITE_NAME = "Microsoft App-v 管理服務"** |
| MANAGEMENT_WEBSITE_PORT | 指定管理服務將使用的埠號碼。 範例用法： **/MANAGEMENT_WEBSITE_PORT = 82** |

#### 管理伺服器資料庫的參數

| 參數 | 資訊 |
|--|--|
| /DB_PREDEPLOY_MANAGEMENT | 指定將安裝管理資料庫。 您必須具備足夠的資料庫許可權，才能完成此安裝。 不需要任何值。 |
| /MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT | 表示應該使用預設的 SQL 實例。 不需要任何值。 |
| /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE | 指定應該用來建立新資料庫的自訂 SQL 實例的名稱。 範例用法： **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**。 如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。 |
| /MANAGEMENT_DB_NAME | 指定應該建立的新管理資料庫的名稱。 範例用法： **/MANAGEMENT_DB_NAME = "AppVMgmtDB"**。 如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。 |
| /MANAGEMENT_SERVER_MACHINE_USE_LOCAL | 指明將存取資料庫的管理伺服器是否已安裝在本機伺服器上。 Switch 參數，因此不需要任何值。 |
| /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT | 指定將安裝管理伺服器的遠端電腦的電腦帳戶。 範例用法： **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\\computername"** |
| /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT | 表示將用於安裝管理伺服器的系統管理員帳戶。 範例用法： **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"** |

#### 安裝發佈伺服器的參數

| 參數 | 資訊 |
|--|--|
| /PUBLISHING_SERVER | 指定將安裝發佈伺服器。 不需要任何值。 |
| /PUBLISHING_MGT_SERVER | 指定發佈伺服器將連接的管理服務的 URL。 範例用法： **HTTP:// &lt; 管理伺服器名稱 &gt; ： &lt; 管理伺服器埠號碼 &gt; **。 如果沒有使用 **/PUBLISHING_SERVER** ，此參數將會被忽略。 |
| /PUBLISHING_WEBSITE_NAME | 指定要針對發佈服務建立的網站名稱。 範例用法： **/PUBLISHING_WEBSITE_NAME = "Microsoft App-v 發佈服務"** |
| /PUBLISHING_WEBSITE_PORT | 指定發佈服務所使用的埠號碼。 範例用法： **/PUBLISHING_WEBSITE_PORT = 83** |

#### 報表伺服器的參數

| 參數 | 資訊 |
|--|--|
| /REPORTING_SERVER | 指定將安裝報表伺服器。 不需要任何值。 |
| /REPORTING_WEBSITE_NAME | 指定要為報表服務建立的網站名稱。 範例用法： **/REPORTING_WEBSITE_NAME = "Microsoft App-v ReportingService"** |
| /REPORTING_WEBSITE_PORT | 指定報表服務將使用的埠號碼。 範例用法： **/REPORTING_WEBSITE_PORT = 82** |

#### 使用現有報表伺服器資料庫的參數

| 參數 | 資訊 |
|--|--|
| /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL | 表示 Microsoft SQL Server 已安裝在本機伺服器上。 Switch 參數，因此不需要任何值。 |
| /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME | 指定安裝 SQL Server 之遠端電腦的名稱。 接受字串。 範例用法： **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"** |
| /EXISTING_ 報告 _DB_SQLINSTANCE_USE_DEFAULT | 表示要使用預設的 SQL 實例。 Switch 參數，因此不需要任何值。 |
| /EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE | 指定應該使用的自訂 SQL 實例的名稱。 接受字串。 範例用法： **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"** |
| /EXISTING_ 報告 _DB_NAME | 指定應該使用之現有報表資料庫的名稱。 接受字串。 範例用法： **/EXISTING_REPORTING_DB_NAME = "AppVReporting"** |

#### 安裝報表伺服器資料庫的參數

| 參數 | 資訊 |
|--|--|
| /DB_PREDEPLOY_REPORTING | 指定將安裝報表資料庫。 此安裝需要擁有 DBA 許可權。 不需要任何值。 |
| /REPORTING_DB_SQLINSTANCE_USE_DEFAULT | 指定應該使用的自訂 SQL 實例的名稱。 接受字串。 範例用法： **/REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"** |
| /REPORTING_DB_NAME | 指定應該建立的新報表資料庫的名稱。 接受字串。 範例用法： **/REPORTING_DB_NAME = "AppVMgmtDB"** |
| /REPORTING_SERVER_MACHINE_USE_LOCAL | 表示將存取資料庫的報表伺服器已安裝在本機伺服器上。 Switch 參數，因此不需要任何值。 |
| /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT | 指定要安裝報表伺服器的遠端電腦的電腦帳戶。 接受字串。 範例用法： **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"** |
| /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT | 表示將用於安裝 App-v 報表服務器的系統管理員帳戶。 接受字串。 範例用法： **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"** |

#### 使用現有管理伺服器資料庫的參數

| 參數 | 資訊 |
|--|--|
| /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL | 表示 SQL Server 已安裝在本機伺服器上。 Switch 參數，因此不需要任何值。如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。 |
| /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME | 指定安裝 SQL Server 之遠端電腦的名稱。 接受字串。 範例用法： **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"** |
| /EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT | 表示要使用預設的 SQL 實例。 Switch 參數，因此不需要任何值。 如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。 |
| /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE | 指定將使用之自訂 SQL 實例的名稱。 範例用法 **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement"**。 如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。 |
| /EXISTING_MANAGEMENT_DB_NAME | 指定應該使用之現有管理資料庫的名稱。 範例用法： **/EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB"**。 如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。 |

有應用程式-V 問題嗎？ 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題

[部署 App-V 5.1 伺服器](deploying-the-app-v-51-server.md)
