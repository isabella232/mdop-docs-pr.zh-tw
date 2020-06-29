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
# <span data-ttu-id="15f56-103">如何使用 SQL 指令碼部署 App-V 資料庫</span><span class="sxs-lookup"><span data-stu-id="15f56-103">How to Deploy the App-V Databases by Using SQL Scripts</span></span>

<span data-ttu-id="15f56-104">使用下列指示來使用 SQL 腳本（而不是 Windows 安裝程式）來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="15f56-104">Use the following instructions to use SQL scripts, rather than the Windows Installer, to:</span></span>

- <span data-ttu-id="15f56-105">安裝 App-v 5.1 資料庫</span><span class="sxs-lookup"><span data-stu-id="15f56-105">Install the App-V 5.1 databases</span></span>
- <span data-ttu-id="15f56-106">將 App-v 資料庫升級至較新的版本</span><span class="sxs-lookup"><span data-stu-id="15f56-106">Upgrade the App-V databases to a later version</span></span>

> [!NOTE]
> <span data-ttu-id="15f56-107">如果您已部署 App-v 5.0 SP3 資料庫，則升級到 App-v 5.1 不需要 SQL 腳本。</span><span class="sxs-lookup"><span data-stu-id="15f56-107">If you have already deployed the App-V 5.0 SP3 database, the SQL scripts are not required to upgrade to App-V 5.1.</span></span>

## <span data-ttu-id="15f56-108">如何使用 SQL 腳本來安裝 App-v 資料庫</span><span class="sxs-lookup"><span data-stu-id="15f56-108">How to install the App-V databases by using SQL scripts</span></span>

1. <span data-ttu-id="15f56-109">在您安裝資料庫腳本之前，請先查看並保留 App-v 授權條款的複本。</span><span class="sxs-lookup"><span data-stu-id="15f56-109">Before you install the database scripts, review and keep a copy of the App-V license terms.</span></span> <span data-ttu-id="15f56-110">透過執行資料庫腳本，您即已同意授權條款。</span><span class="sxs-lookup"><span data-stu-id="15f56-110">By running the database scripts, you are agreeing to the license terms.</span></span> <span data-ttu-id="15f56-111">如果您不接受，請不要使用這個軟體。</span><span class="sxs-lookup"><span data-stu-id="15f56-111">If you do not accept them, you should not use this software.</span></span>
1. <span data-ttu-id="15f56-112">將**appv\_server\_setup.exe**從 app-v 版本媒體複製到臨時位置。</span><span class="sxs-lookup"><span data-stu-id="15f56-112">Copy the **appv\_server\_setup.exe** from the App-V release media to a temporary location.</span></span>
1. <span data-ttu-id="15f56-113">從命令提示字元執行**appv\_server\_setup.exe** ，並指定解壓縮資料庫腳本的臨時位置。</span><span class="sxs-lookup"><span data-stu-id="15f56-113">From a command prompt, run **appv\_server\_setup.exe** and specify a temporary location for extracting the database scripts.</span></span>

    <span data-ttu-id="15f56-114">範例： appv\_server\_setup.exe/layout c:\\ &lt; _臨時位置路徑_&gt;</span><span class="sxs-lookup"><span data-stu-id="15f56-114">Example: appv\_server\_setup.exe /layout c:\\&lt;_temporary location path_&gt;</span></span>

1. <span data-ttu-id="15f56-115">流覽至您建立的臨時位置，開啟 [提取的**DatabaseScripts** ] 資料夾，然後查看適當的 Readme.txt 檔案以取得相關指示：</span><span class="sxs-lookup"><span data-stu-id="15f56-115">Browse to the temporary location that you created, open the extracted **DatabaseScripts** folder, and review the appropriate Readme.txt file for instructions:</span></span>

    | <span data-ttu-id="15f56-116">資料庫</span><span class="sxs-lookup"><span data-stu-id="15f56-116">Database</span></span> | <span data-ttu-id="15f56-117">要使用 Readme.txt 檔案的位置</span><span class="sxs-lookup"><span data-stu-id="15f56-117">Location of Readme.txt file to use</span></span> |
    |--|--|
    | <span data-ttu-id="15f56-118">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="15f56-118">Management database</span></span> | <span data-ttu-id="15f56-119">ManagementDatabase 子資料夾</span><span class="sxs-lookup"><span data-stu-id="15f56-119">ManagementDatabase subfolder</span></span> |
    | <span data-ttu-id="15f56-120">報表資料庫</span><span class="sxs-lookup"><span data-stu-id="15f56-120">Reporting database</span></span> | <span data-ttu-id="15f56-121">ReportingDatabase 子資料夾</span><span class="sxs-lookup"><span data-stu-id="15f56-121">ReportingDatabase subfolder</span></span> |

> [!CAUTION]
> <span data-ttu-id="15f56-122">ManagementDatabase 子資料夾中的 readme.txt 檔案已過期。</span><span class="sxs-lookup"><span data-stu-id="15f56-122">The readme.txt file in the ManagementDatabase subfolder is out of date.</span></span> <span data-ttu-id="15f56-123">下列更新之 readme 檔案中的資訊是最新的，而且應該取代**DatabaseScripts**資料夾中提供的讀我檔案資訊。</span><span class="sxs-lookup"><span data-stu-id="15f56-123">The information in the updated readme files below is the most current and should supersede the readme information provided in the **DatabaseScripts** folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15f56-124">在 app-v 5.0 SP3 之後的 App-v management 資料庫版本中，不需要 InsertVersionInfo 腳本。</span><span class="sxs-lookup"><span data-stu-id="15f56-124">The InsertVersionInfo.sql script is not required for versions of the App-V management database later than App-V 5.0 SP3.</span></span>

<span data-ttu-id="15f56-125">必須依據[知識庫文章 3031340](https://support.microsoft.com/kb/3031340)中的**步驟 2**來更新 [sql 腳本]。</span><span class="sxs-lookup"><span data-stu-id="15f56-125">The Permissions.sql script should be updated according to **Step 2** in [KB article 3031340](https://support.microsoft.com/kb/3031340).</span></span> <span data-ttu-id="15f56-126">在 app-v 5.0 SP3 的版本之後，不需要**步驟 1** 。</span><span class="sxs-lookup"><span data-stu-id="15f56-126">**Step 1** is not required for versions of App-V later than App-V 5.0 SP3.</span></span>

## <span data-ttu-id="15f56-127">更新的管理資料庫讀我檔案內容</span><span class="sxs-lookup"><span data-stu-id="15f56-127">Updated management database README file content</span></span>

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

## <span data-ttu-id="15f56-128">已更新的報表資料庫讀我檔案內容</span><span class="sxs-lookup"><span data-stu-id="15f56-128">Updated reporting database README file content</span></span>

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

**<span data-ttu-id="15f56-129">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="15f56-129">Got an App-V issue?</span></span>** <span data-ttu-id="15f56-130">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="15f56-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="15f56-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="15f56-131">Related topics</span></span>

[<span data-ttu-id="15f56-132">部署 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="15f56-132">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

[<span data-ttu-id="15f56-133">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="15f56-133">How to Deploy the App-V 5.1 Server</span></span>](how-to-deploy-the-app-v-51-server.md)
