---
title: 如何使用 SQL 指令碼部署 App-V 資料庫
description: 如何使用 SQL 指令碼部署 App-V 資料庫
author: dansimp
ms.assetid: 1183b1bc-d4d7-4914-a049-06e82bf2d96d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4695d105c1aa6732efb6b8ed05169cf29e7f972b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800510"
---
# 如何使用 SQL 指令碼部署 App-V 資料庫

使用下列指示來使用 SQL 腳本（而不是 Windows 安裝程式）來執行下列作業：

- 安裝 App-v 5.1 資料庫
- 將 App-v 資料庫升級至較新的版本

> [!NOTE]
> 如果您已部署 App-v 5.0 SP3 資料庫，則升級到 App-v 5.1 不需要 SQL 腳本。

## 如何使用 SQL 腳本來安裝 App-v 資料庫

1. 在您安裝資料庫腳本之前，請先查看並保留 App-v 授權條款的複本。 透過執行資料庫腳本，您即已同意授權條款。 如果您不接受，請不要使用這個軟體。
1. 將**appv\_server\_setup.exe**從 app-v 版本媒體複製到臨時位置。
1. 從命令提示字元執行**appv\_server\_setup.exe** ，並指定解壓縮資料庫腳本的臨時位置。

    範例： appv\_server\_setup.exe/layout c:\\ &lt; _臨時位置路徑_&gt;

1. 流覽至您建立的臨時位置，開啟 [提取的**DatabaseScripts** ] 資料夾，然後查看適當的 Readme.txt 檔案以取得相關指示：

    | 資料庫 | 要使用 Readme.txt 檔案的位置 |
    |--|--|
    | 管理資料庫 | ManagementDatabase 子資料夾 |
    | 報表資料庫 | ReportingDatabase 子資料夾 |

> [!CAUTION]
> ManagementDatabase 子資料夾中的 readme.txt 檔案已過期。 下列更新之 readme 檔案中的資訊是最新的，而且應該取代**DatabaseScripts**資料夾中提供的讀我檔案資訊。

> [!IMPORTANT]
> 在 app-v 5.0 SP3 之後的 App-v management 資料庫版本中，不需要 InsertVersionInfo 腳本。

必須依據[知識庫文章 3031340](https://support.microsoft.com/kb/3031340)中的**步驟 2**來更新 [sql 腳本]。 在 app-v 5.0 SP3 的版本之後，不需要**步驟 1** 。

## 更新的管理資料庫讀我檔案內容

```plaintext
******************************************************************
Before you install and use the Application Virtualization Database Scripts you must:
1.Review the Microsoft Application Virtualization Server 5.0 license terms.
2.Print and retain a copy of the license terms for your records.
By running the Microsoft Application Virtualization Database Scripts you agree to such license terms.  If you do not accept them, do not use the software.
******************************************************************


Steps to install "AppVManagement" schema in SQL SERVER.


## PREREQUISITES:

 1. Review the installation package.  The following files MUST exist:

    SQL files
    ---------
    Database.sql
    CreateTables.sql
    CreateStoredProcs.sql
    UpdateTables.sql
    Permissions.sql

 2. Ensure the target SQL Server instance and SQL Server Agent service are running.

 3. If you are not running the scripts directly on the server, ensure the
    necessary SQL Server client software is installed and available from
    the specified location.  Specifically, the "osql" command must
##     be supported for these scripts to run.



## PREPARATION:

 1. Review the database.sql file and modify as necessary.  Although the
    defaults are likely sufficient, it is suggested that the following
    settings be reviewed:

    DATABASE - ensure name is satisfactory - default is "AppVManagement".

 2. Review the Permissions.sql file and provide all the necessary account information
    for setting up read and write access on the database. Note: Default settings
##     in the file will not work.



## INSTALLATION:

 1. Run the database.sql against the "master" database.  Your user
    credential must have the ability to create databases.
    This script will create the database.

 2. Run the following scripts against the "AppVManagement" database using the
    same account as above in order.

    CreateTables.sql
    CreateStoredProcs.sql
    UpdateTables.sql
##     Permissions.sql

```

## 已更新的報表資料庫讀我檔案內容

```plaintext
******************************************************************
Before you install and use the Application Virtualization Database Scripts you must:
1.Review the Microsoft Application Virtualization Server 5.0 license terms.
2.Print and retain a copy of the license terms for your records.
By running the Microsoft Application Virtualization Database Scripts you agree to such license terms.  If you do not accept them, do not use the software.
******************************************************************

Steps to install "AppVReporting" schema in SQL SERVER.


## PREREQUISITES:

 1. Review the installation package.  The following files MUST exist:

    SQL files
    ---------
    Database.sql
    UpgradeDatabase.sql
    CreateTables.sql
    CreateReportingStoredProcs.sql
    CreateStoredProcs.sql
    CreateViews.sql
    InsertVersionInfo.sql
    Permissions.sql
    ScheduleReportingJob.sql

 2. Ensure the target SQL Server instance and SQL Server Agent service are running.

 3. If you are not running the scripts directly on the server, ensure the 
    necessary SQL Server client software is installed and executable from
    the location you have chosen.  Specifically, the "osql" command must
##     be supported for these scripts to run.



## PREPARATION:

 1. Review the database.sql file and modify as necessary.  Although the
    defaults are likely sufficient, it is suggested that the following
    settings be reviewed:

    DATABASE - ensure name is satisfactory - default is "AppVReporting".

 2. Review the Permissions.sql file and provide all the necessary account information
    for setting up read and write access on the database. Note: Default settings
    in the file will not work.

 3. Review the ScheduleReportingJob.sql file and make sure that the stored proc schedule
    time is acceptable. The default stored proc schedule time is at 12.01 AM (line 84). 
    If this time is not suitable, you can change this to a more suitable time. The time is
##     in the format HHMMSS.



## INSTALLATION:

 1. Run the database.sql against the "master" database.  Your user
    credential must have the ability to create databases.
    This script will create the database.

 2. If upgrading the database, run UpgradeDatabase.sql This will upgrade database schema.

 2. Run the following scripts against the "AppVReporting" database using the
    same account as above in order.

    CreateTables.sql
    CreateReportingStoredProcs.sql
    CreateStoredProcs.sql
    CreateViews.sql
    InsertVersionInfo.sql
    Permissions.sql
##     ScheduleReportingJob.sql

```

**有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題

[部署 App-V 5.1 伺服器](deploying-the-app-v-51-server.md)

[如何部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)
