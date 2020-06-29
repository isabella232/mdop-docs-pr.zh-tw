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
# <span data-ttu-id="fb169-103">如何使用指令碼來部署 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-103">How to Deploy the App-V 5.1 Server Using a Script</span></span>

<span data-ttu-id="fb169-104">若要使用命令列成功完成**appv\_server\_setup.exe**伺服器設定，您必須指定併合並多個參數。</span><span class="sxs-lookup"><span data-stu-id="fb169-104">In order to complete the **appv\_server\_setup.exe** Server setup successfully using the command line, you must specify and combine multiple parameters.</span></span>

## <span data-ttu-id="fb169-105">使用腳本安裝 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-105">Install the App-V 5.1 server using a script</span></span>

- <span data-ttu-id="fb169-106">使用命令列來安裝 App-V 5.1 伺服器的下列資訊。</span><span class="sxs-lookup"><span data-stu-id="fb169-106">Use the following information about installing the App-V 5.1 server using the command line.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb169-107">您也可以使用命令列來存取下清單格中的資訊，方法是輸入以下命令： **appv\_server\_setup.exe/？**。</span><span class="sxs-lookup"><span data-stu-id="fb169-107">The information in the following tables can also be accessed using the command line by typing the following command: **appv\_server\_setup.exe /?**.</span></span>

### <span data-ttu-id="fb169-108">在本機電腦上安裝管理伺服器與管理資料庫</span><span class="sxs-lookup"><span data-stu-id="fb169-108">Install the Management server and Management database on a local machine</span></span>

<span data-ttu-id="fb169-109">下列參數對於 Microsoft SQL Server 的預設與自訂實例都是有效的：</span><span class="sxs-lookup"><span data-stu-id="fb169-109">The following parameters are valid with both the default and custom instance of Microsoft SQL Server:</span></span>

- <span data-ttu-id="fb169-110">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-110">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="fb169-111">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-111">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="fb169-112">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-112">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-113">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-113">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-114">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="fb169-114">/DB_PREDEPLOY_MANAGEMENT</span></span>
- <span data-ttu-id="fb169-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>
- <span data-ttu-id="fb169-116">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-116">/MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="fb169-117">範例：使用 Microsoft SQL Server 的自訂實例</span><span class="sxs-lookup"><span data-stu-id="fb169-117">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement"
```

### <span data-ttu-id="fb169-118">在本機電腦上使用現有的管理資料庫來安裝管理伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-118">Install the Management server using an existing Management database on a local machine</span></span>

<span data-ttu-id="fb169-119">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-119">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-120">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-120">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="fb169-121">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-121">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="fb169-122">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-122">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-123">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-123">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-124">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-124">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="fb169-125">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-125">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-126">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-126">/EXISTING_MANAGEMENT_DB_NAME</span></span>

<span data-ttu-id="fb169-127">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-127">To use a custom instance of Microsoft SQL Server, use the following parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-128">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-128">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="fb169-129">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-129">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="fb169-130">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-130">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-131">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-131">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-132">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-132">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="fb169-133">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-133">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-134">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-134">/EXISTING_MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="fb169-135">範例：使用 Microsoft SQL Server 的自訂實例</span><span class="sxs-lookup"><span data-stu-id="fb169-135">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### <span data-ttu-id="fb169-136">在遠端電腦上使用現有的管理資料庫來安裝管理伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-136">Install the Management server using an existing Management database on a remote machine</span></span>

<span data-ttu-id="fb169-137">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-137">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-138">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-138">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="fb169-139">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-139">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="fb169-140">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-140">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-141">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-141">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-142">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-142">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="fb169-143">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-143">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-144">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-144">/EXISTING_MANAGEMENT_DB_NAME</span></span>

<span data-ttu-id="fb169-145">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-145">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-146">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-146">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="fb169-147">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-147">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="fb169-148">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-148">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-149">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-149">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-150">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-150">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="fb169-151">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-151">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-152">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-152">/EXISTING_MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="fb169-153">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-153">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME="SqlServermachine.domainName" /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### <span data-ttu-id="fb169-154">在同一部電腦上安裝管理資料庫和管理伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-154">Install the Management database and the Management Server on the same computer</span></span>

<span data-ttu-id="fb169-155">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-155">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-156">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="fb169-156">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="fb169-157">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-157">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-158">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-158">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="fb169-159">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-159">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="fb169-160">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-160">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="fb169-161">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-161">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-162">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="fb169-162">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="fb169-163">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-163">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-164">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-164">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="fb169-165">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-165">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="fb169-166">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-166">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="fb169-167">範例：使用 Microsoft SQL Server 的自訂實例</span><span class="sxs-lookup"><span data-stu-id="fb169-167">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_SERVER_MACHINE_USE_LOCAL /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="fb169-168">在與管理伺服器不同的電腦上安裝管理資料庫</span><span class="sxs-lookup"><span data-stu-id="fb169-168">Install the Management database on a different computer than the Management server</span></span>

<span data-ttu-id="fb169-169">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-169">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-170">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="fb169-170">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="fb169-171">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-171">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-172">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-172">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="fb169-173">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-173">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="fb169-174">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-174">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="fb169-175">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-175">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-176">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="fb169-176">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="fb169-177">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-177">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-178">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-178">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="fb169-179">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-179">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="fb169-180">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-180">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="fb169-181">範例：使用 Microsoft SQL Server 的自訂實例</span><span class="sxs-lookup"><span data-stu-id="fb169-181">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="fb169-182">安裝發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-182">Install the publishing server</span></span>

<span data-ttu-id="fb169-183">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="fb169-183">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span>

- <span data-ttu-id="fb169-184">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-184">/PUBLISHING_SERVER</span></span>
- <span data-ttu-id="fb169-185">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-185">/PUBLISHING_MGT_SERVER</span></span>
- <span data-ttu-id="fb169-186">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-186">/PUBLISHING_WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-187">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-187">/PUBLISHING_WEBSITE_PORT</span></span>

**<span data-ttu-id="fb169-188">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-188">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /PUBLISHING_SERVER /PUBLISHING_MGT_SERVER="http://ManagementServerName:ManagementPort" /PUBLISHING_WEBSITE_NAME="Microsoft AppV Publishing Service" /PUBLISHING_WEBSITE_PORT="8081"
```

### <span data-ttu-id="fb169-189">在本機電腦上安裝報表伺服器與報告資料庫</span><span class="sxs-lookup"><span data-stu-id="fb169-189">Install the Reporting server and Reporting database on a local machine</span></span>

<span data-ttu-id="fb169-190">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-190">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-191">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-191">/REPORTING _SERVER</span></span>
- <span data-ttu-id="fb169-192">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-192">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-193">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-193">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-194">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-194">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="fb169-195">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-195">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-196">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-196">/REPORTING _DB_NAME</span></span>

<span data-ttu-id="fb169-197">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-197">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-198">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-198">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="fb169-199">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-199">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="fb169-200">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-200">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-201">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-201">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-202">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-202">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="fb169-203">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-203">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-204">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-204">/REPORTING _DB_NAME</span></span>

**<span data-ttu-id="fb169-205">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-205">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="fb169-206">在本機電腦上安裝報表伺服器並使用現有的報表資料庫</span><span class="sxs-lookup"><span data-stu-id="fb169-206">Install the Reporting server and using an existing Reporting database on a local machine</span></span>

<span data-ttu-id="fb169-207">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-207">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-208">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-208">/REPORTING _SERVER</span></span>
- <span data-ttu-id="fb169-209">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-209">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-210">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-210">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-211">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-211">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="fb169-212">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-212">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-213">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-213">/EXISTING_REPORTING _DB_NAME</span></span>

<span data-ttu-id="fb169-214">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-214">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-215">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-215">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="fb169-216">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-216">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="fb169-217">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-217">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-218">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-218">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-219">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-219">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="fb169-220">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-220">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-221">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-221">/EXISTING_REPORTING _DB_NAME</span></span>

**<span data-ttu-id="fb169-222">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-222">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="fb169-223">在遠端電腦上使用現有的報表資料庫來安裝報表伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-223">Install the Reporting server using an existing Reporting database on a remote machine</span></span>

<span data-ttu-id="fb169-224">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-224">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-225">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-225">/REPORTING _SERVER</span></span>
- <span data-ttu-id="fb169-226">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-226">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-227">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-227">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-228">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-228">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="fb169-229">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-229">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-230">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-230">/EXISTING_REPORTING _DB_NAME</span></span>

<span data-ttu-id="fb169-231">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-231">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-232">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-232">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="fb169-233">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-233">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="fb169-234">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-234">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="fb169-235">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-235">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="fb169-236">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-236">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="fb169-237">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-237">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-238">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-238">/EXISTING_REPORTING _DB_NAME</span></span>

**<span data-ttu-id="fb169-239">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-239">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME="SqlServerMachine.DomainName" /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="fb169-240">在報表伺服器所在的電腦上安裝報表資料庫</span><span class="sxs-lookup"><span data-stu-id="fb169-240">Install the Reporting database on the same computer as the Reporting server</span></span>

<span data-ttu-id="fb169-241">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-241">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-242">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-242">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="fb169-243">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-243">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="fb169-244">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-244">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="fb169-245">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-245">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="fb169-246">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-246">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="fb169-247">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-247">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-248">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-248">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="fb169-249">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-249">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="fb169-250">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-250">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="fb169-251">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-251">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="fb169-252">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-252">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="fb169-253">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-253">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_SERVER_MACHINE_USE_LOCAL /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="fb169-254">在不同的電腦上安裝報表資料庫，而不是報表伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-254">Install the Reporting database on a different computer than the Reporting server</span></span>

<span data-ttu-id="fb169-255">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數（與自訂實例在*斜體*中的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-255">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="fb169-256">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-256">/DB_PREDEPLOY_REPORTING</span></span>
- <span data-ttu-id="fb169-257">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-257">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>
- <span data-ttu-id="fb169-258">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-258">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="fb169-259">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-259">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="fb169-260">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-260">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="fb169-261">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數（以*斜體*顯示預設實例的差異）：</span><span class="sxs-lookup"><span data-stu-id="fb169-261">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="fb169-262">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-262">/DB_PREDEPLOY_REPORTING</span></span>
- <span data-ttu-id="fb169-263">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-263">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>
- <span data-ttu-id="fb169-264">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-264">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="fb169-265">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-265">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="fb169-266">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-266">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="fb169-267">範例：使用 Microsoft SQL Server 的自訂實例：</span><span class="sxs-lookup"><span data-stu-id="fb169-267">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
 appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="fb169-268">參數定義</span><span class="sxs-lookup"><span data-stu-id="fb169-268">Parameter Definitions</span></span>

#### <span data-ttu-id="fb169-269">一般參數</span><span class="sxs-lookup"><span data-stu-id="fb169-269">General Parameters</span></span>

| <span data-ttu-id="fb169-270">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-270">Parameter</span></span> | <span data-ttu-id="fb169-271">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-271">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-272">/QUIET</span><span class="sxs-lookup"><span data-stu-id="fb169-272">/QUIET</span></span> | <span data-ttu-id="fb169-273">指定 [緘默安裝]。</span><span class="sxs-lookup"><span data-stu-id="fb169-273">Specifies silent install.</span></span> |
| <span data-ttu-id="fb169-274">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="fb169-274">/UNINSTALL</span></span> | <span data-ttu-id="fb169-275">指定卸載。</span><span class="sxs-lookup"><span data-stu-id="fb169-275">Specifies an uninstall.</span></span> |
| <span data-ttu-id="fb169-276">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="fb169-276">/LAYOUT</span></span> | <span data-ttu-id="fb169-277">指定 [版面配置] 動作。</span><span class="sxs-lookup"><span data-stu-id="fb169-277">Specifies layout action.</span></span> <span data-ttu-id="fb169-278">這會將 MSIs 和腳本檔案解壓縮至資料夾，而不會實際安裝產品。</span><span class="sxs-lookup"><span data-stu-id="fb169-278">This extracts the MSIs and script files to a folder without actually installing the product.</span></span> <span data-ttu-id="fb169-279">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-279">No value is expected.</span></span> |
| <span data-ttu-id="fb169-280">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="fb169-280">/LAYOUTDIR</span></span> | <span data-ttu-id="fb169-281">指定版面配置目錄。</span><span class="sxs-lookup"><span data-stu-id="fb169-281">Specifies the layout directory.</span></span> <span data-ttu-id="fb169-282">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-282">Takes a string.</span></span> <span data-ttu-id="fb169-283">範例用法： **/LAYOUTDIR = "C:\\Application Virtualization 伺服器"**</span><span class="sxs-lookup"><span data-stu-id="fb169-283">Example usage: **/LAYOUTDIR="C:\\Application Virtualization Server"**</span></span> |
| <span data-ttu-id="fb169-284">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="fb169-284">/INSTALLDIR</span></span> | <span data-ttu-id="fb169-285">指定安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="fb169-285">Specifies the installation directory.</span></span> <span data-ttu-id="fb169-286">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-286">Takes a string.</span></span> <span data-ttu-id="fb169-287">範例用法： **/INSTALLDIR = "C:\\program files Files\\Application Virtualization\\Server"**</span><span class="sxs-lookup"><span data-stu-id="fb169-287">Example usage: **/INSTALLDIR="C:\\Program Files\\Application Virtualization\\Server"**</span></span> |
| <span data-ttu-id="fb169-288">/MUOPTIN</span><span class="sxs-lookup"><span data-stu-id="fb169-288">/MUOPTIN</span></span> | <span data-ttu-id="fb169-289">啟用 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="fb169-289">Enables Microsoft Update.</span></span> <span data-ttu-id="fb169-290">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-290">No value is expected.</span></span> |
| <span data-ttu-id="fb169-291">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="fb169-291">/ACCEPTEULA</span></span> | <span data-ttu-id="fb169-292">接受授權合約。</span><span class="sxs-lookup"><span data-stu-id="fb169-292">Accepts the license agreement.</span></span> <span data-ttu-id="fb169-293">這對於無操作安裝是必要的。</span><span class="sxs-lookup"><span data-stu-id="fb169-293">This is required for an unattended installation.</span></span> <span data-ttu-id="fb169-294">範例用法： **/ACCEPTEULA**或 **/ACCEPTEULA = 1**</span><span class="sxs-lookup"><span data-stu-id="fb169-294">Example usage: **/ACCEPTEULA** or **/ACCEPTEULA=1**</span></span> |

#### <span data-ttu-id="fb169-295">管理伺服器安裝參數</span><span class="sxs-lookup"><span data-stu-id="fb169-295">Management Server Installation Parameters</span></span>

|<span data-ttu-id="fb169-296">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-296">Parameter</span></span> |<span data-ttu-id="fb169-297">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-297">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-298">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-298">/MANAGEMENT_SERVER</span></span> | <span data-ttu-id="fb169-299">指定將安裝管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb169-299">Specifies that the management server will be installed.</span></span> <span data-ttu-id="fb169-300">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="fb169-300">No value is expected</span></span> |
| <span data-ttu-id="fb169-301">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-301">/MANAGEMENT_ADMINACCOUNT</span></span> | <span data-ttu-id="fb169-302">指定允許系統管理員存取管理伺服器的帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb169-302">Specifies the account that will be allowed Administrator access to the management server.</span></span> <span data-ttu-id="fb169-303">這可以是使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="fb169-303">This can be a user account or a group.</span></span> <span data-ttu-id="fb169-304">範例用法： **/MANAGEMENT_ADMINACCOUNT = "mydomain\\admin"**。</span><span class="sxs-lookup"><span data-stu-id="fb169-304">Example usage: **/MANAGEMENT_ADMINACCOUNT="mydomain\\admin"**.</span></span> <span data-ttu-id="fb169-305">如果未指定 **/MANAGEMENT_SERVER** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-305">If **/MANAGEMENT_SERVER** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="fb169-306">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-306">/MANAGEMENT_WEBSITE_NAME</span></span> | <span data-ttu-id="fb169-307">指定將為管理服務建立的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-307">Specifies name of the website that will be created for the management service.</span></span> <span data-ttu-id="fb169-308">範例用法： **/MANAGEMENT_WEBSITE_NAME = "Microsoft App-v 管理服務"**</span><span class="sxs-lookup"><span data-stu-id="fb169-308">Example usage: **/MANAGEMENT_WEBSITE_NAME="Microsoft App-V Management Service"**</span></span> |
| <span data-ttu-id="fb169-309">MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-309">MANAGEMENT_WEBSITE_PORT</span></span> | <span data-ttu-id="fb169-310">指定管理服務將使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fb169-310">Specifies the port number that will be used by the management service will use.</span></span> <span data-ttu-id="fb169-311">範例用法： **/MANAGEMENT_WEBSITE_PORT = 82**</span><span class="sxs-lookup"><span data-stu-id="fb169-311">Example usage: **/MANAGEMENT_WEBSITE_PORT=82**</span></span> |

#### <span data-ttu-id="fb169-312">管理伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="fb169-312">Parameters for the Management Server Database</span></span>

| <span data-ttu-id="fb169-313">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-313">Parameter</span></span> | <span data-ttu-id="fb169-314">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-314">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-315">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="fb169-315">/DB_PREDEPLOY_MANAGEMENT</span></span> | <span data-ttu-id="fb169-316">指定將安裝管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="fb169-316">Specifies that the management database will be installed.</span></span> <span data-ttu-id="fb169-317">您必須具備足夠的資料庫許可權，才能完成此安裝。</span><span class="sxs-lookup"><span data-stu-id="fb169-317">You must have sufficient database permissions to complete this installation.</span></span> <span data-ttu-id="fb169-318">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-318">No value is expected.</span></span> |
| <span data-ttu-id="fb169-319">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-319">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="fb169-320">表示應該使用預設的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="fb169-320">Indicates that the default SQL instance should be used.</span></span> <span data-ttu-id="fb169-321">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-321">No value is expected.</span></span> |
| <span data-ttu-id="fb169-322">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-322">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="fb169-323">指定應該用來建立新資料庫的自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-323">Specifies the name of the custom SQL instance that should be used to create a new database.</span></span> <span data-ttu-id="fb169-324">範例用法： **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**。</span><span class="sxs-lookup"><span data-stu-id="fb169-324">Example usage: **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**.</span></span> <span data-ttu-id="fb169-325">如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-325">If **/DB_PREDEPLOY_MANAGEMENT** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="fb169-326">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-326">/MANAGEMENT_DB_NAME</span></span> | <span data-ttu-id="fb169-327">指定應該建立的新管理資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-327">Specifies the name of the new management database that should be created.</span></span> <span data-ttu-id="fb169-328">範例用法： **/MANAGEMENT_DB_NAME = "AppVMgmtDB"**。</span><span class="sxs-lookup"><span data-stu-id="fb169-328">Example usage: **/MANAGEMENT_DB_NAME="AppVMgmtDB"**.</span></span> <span data-ttu-id="fb169-329">如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-329">If **/DB_PREDEPLOY_MANAGEMENT** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="fb169-330">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-330">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span> | <span data-ttu-id="fb169-331">指明將存取資料庫的管理伺服器是否已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fb169-331">Indicates if the management server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="fb169-332">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-332">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="fb169-333">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-333">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span> | <span data-ttu-id="fb169-334">指定將安裝管理伺服器的遠端電腦的電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb169-334">Specifies the machine account of the remote machine that the management server will be installed on.</span></span> <span data-ttu-id="fb169-335">範例用法： **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\\computername"**</span><span class="sxs-lookup"><span data-stu-id="fb169-335">Example usage: **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="domain\\computername"**</span></span> |
| <span data-ttu-id="fb169-336">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-336">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span> | <span data-ttu-id="fb169-337">表示將用於安裝管理伺服器的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb169-337">Indicates the Administrator account that will be used to install the management server.</span></span> <span data-ttu-id="fb169-338">範例用法： **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"**</span><span class="sxs-lookup"><span data-stu-id="fb169-338">Example usage: **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT ="domain\\alias"**</span></span> |

#### <span data-ttu-id="fb169-339">安裝發佈伺服器的參數</span><span class="sxs-lookup"><span data-stu-id="fb169-339">Parameters for Installing Publishing Server</span></span>

| <span data-ttu-id="fb169-340">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-340">Parameter</span></span> | <span data-ttu-id="fb169-341">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-341">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-342">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-342">/PUBLISHING_SERVER</span></span> | <span data-ttu-id="fb169-343">指定將安裝發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb169-343">Specifies that the Publishing Server will be installed.</span></span> <span data-ttu-id="fb169-344">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-344">No value is expected.</span></span> |
| <span data-ttu-id="fb169-345">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-345">/PUBLISHING_MGT_SERVER</span></span> | <span data-ttu-id="fb169-346">指定發佈伺服器將連接的管理服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="fb169-346">Specifies the URL to Management Service the Publishing server will connect to.</span></span> <span data-ttu-id="fb169-347">範例用法： \*\*HTTP:// &lt; 管理伺服器名稱 &gt; ： &lt; 管理伺服器埠號碼 &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="fb169-347">Example usage: **http://&lt;management server name&gt;:&lt;Management server port number&gt;**.</span></span> <span data-ttu-id="fb169-348">如果沒有使用 **/PUBLISHING_SERVER** ，此參數將會被忽略。</span><span class="sxs-lookup"><span data-stu-id="fb169-348">If **/PUBLISHING_SERVER** is not used, this parameter will be ignored.</span></span> |
| <span data-ttu-id="fb169-349">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-349">/PUBLISHING_WEBSITE_NAME</span></span> | <span data-ttu-id="fb169-350">指定要針對發佈服務建立的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-350">Specifies name of the website that will be created for the publishing service.</span></span> <span data-ttu-id="fb169-351">範例用法： **/PUBLISHING_WEBSITE_NAME = "Microsoft App-v 發佈服務"**</span><span class="sxs-lookup"><span data-stu-id="fb169-351">Example usage: **/PUBLISHING_WEBSITE_NAME="Microsoft App-V Publishing Service"**</span></span> |
| <span data-ttu-id="fb169-352">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-352">/PUBLISHING_WEBSITE_PORT</span></span> | <span data-ttu-id="fb169-353">指定發佈服務所使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fb169-353">Specifies the port number used by the publishing service.</span></span> <span data-ttu-id="fb169-354">範例用法： **/PUBLISHING_WEBSITE_PORT = 83**</span><span class="sxs-lookup"><span data-stu-id="fb169-354">Example usage: **/PUBLISHING_WEBSITE_PORT=83**</span></span> |

#### <span data-ttu-id="fb169-355">報表伺服器的參數</span><span class="sxs-lookup"><span data-stu-id="fb169-355">Parameters for Reporting Server</span></span>

| <span data-ttu-id="fb169-356">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-356">Parameter</span></span> | <span data-ttu-id="fb169-357">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-357">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-358">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="fb169-358">/REPORTING_SERVER</span></span> | <span data-ttu-id="fb169-359">指定將安裝報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb169-359">Specifies that the Reporting Server will be installed.</span></span> <span data-ttu-id="fb169-360">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-360">No value is expected.</span></span> |
| <span data-ttu-id="fb169-361">/REPORTING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-361">/REPORTING_WEBSITE_NAME</span></span> | <span data-ttu-id="fb169-362">指定要為報表服務建立的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-362">Specifies name of the website that will be created for the Reporting Service.</span></span> <span data-ttu-id="fb169-363">範例用法： **/REPORTING_WEBSITE_NAME = "Microsoft App-v ReportingService"**</span><span class="sxs-lookup"><span data-stu-id="fb169-363">Example usage: **/REPORTING_WEBSITE_NAME="Microsoft App-V ReportingService"**</span></span> |
| <span data-ttu-id="fb169-364">/REPORTING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="fb169-364">/REPORTING_WEBSITE_PORT</span></span> | <span data-ttu-id="fb169-365">指定報表服務將使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fb169-365">Specifies the port number that the Reporting Service will use.</span></span> <span data-ttu-id="fb169-366">範例用法： **/REPORTING_WEBSITE_PORT = 82**</span><span class="sxs-lookup"><span data-stu-id="fb169-366">Example usage: **/REPORTING_WEBSITE_PORT=82**</span></span> |

#### <span data-ttu-id="fb169-367">使用現有報表伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="fb169-367">Parameters for using an Existing Reporting Server Database</span></span>

| <span data-ttu-id="fb169-368">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-368">Parameter</span></span> | <span data-ttu-id="fb169-369">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-369">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-370">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-370">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span> | <span data-ttu-id="fb169-371">表示 Microsoft SQL Server 已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fb169-371">Indicates that the Microsoft SQL Server is installed on the local server.</span></span> <span data-ttu-id="fb169-372">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-372">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="fb169-373">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-373">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span> | <span data-ttu-id="fb169-374">指定安裝 SQL Server 之遠端電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-374">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="fb169-375">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-375">Takes a string.</span></span> <span data-ttu-id="fb169-376">範例用法： **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"**</span><span class="sxs-lookup"><span data-stu-id="fb169-376">Example usage: **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME="mycomputer1"**</span></span> |
| <span data-ttu-id="fb169-377">/EXISTING_ 報告 _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-377">/EXISTING_ REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="fb169-378">表示要使用預設的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="fb169-378">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="fb169-379">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-379">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="fb169-380">/EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-380">/EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="fb169-381">指定應該使用的自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-381">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="fb169-382">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-382">Takes a string.</span></span> <span data-ttu-id="fb169-383">範例用法： **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**</span><span class="sxs-lookup"><span data-stu-id="fb169-383">Example usage: **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**</span></span> |
| <span data-ttu-id="fb169-384">/EXISTING_ 報告 _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-384">/EXISTING_ REPORTING _DB_NAME</span></span> | <span data-ttu-id="fb169-385">指定應該使用之現有報表資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-385">Specifies the name of the existing Reporting database that should be used.</span></span> <span data-ttu-id="fb169-386">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-386">Takes a string.</span></span> <span data-ttu-id="fb169-387">範例用法： **/EXISTING_REPORTING_DB_NAME = "AppVReporting"**</span><span class="sxs-lookup"><span data-stu-id="fb169-387">Example usage: **/EXISTING_REPORTING_DB_NAME="AppVReporting"**</span></span> |

#### <span data-ttu-id="fb169-388">安裝報表伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="fb169-388">Parameters for installing Reporting Server Database</span></span>

| <span data-ttu-id="fb169-389">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-389">Parameter</span></span> | <span data-ttu-id="fb169-390">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-390">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-391">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="fb169-391">/DB_PREDEPLOY_REPORTING</span></span> | <span data-ttu-id="fb169-392">指定將安裝報表資料庫。</span><span class="sxs-lookup"><span data-stu-id="fb169-392">Specifies that the Reporting Database will be installed.</span></span> <span data-ttu-id="fb169-393">此安裝需要擁有 DBA 許可權。</span><span class="sxs-lookup"><span data-stu-id="fb169-393">DBA permissions are required for this installation.</span></span> <span data-ttu-id="fb169-394">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-394">No value is expected.</span></span> |
| <span data-ttu-id="fb169-395">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-395">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="fb169-396">指定應該使用的自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-396">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="fb169-397">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-397">Takes a string.</span></span> <span data-ttu-id="fb169-398">範例用法： **/REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**</span><span class="sxs-lookup"><span data-stu-id="fb169-398">Example usage: **/REPORTING_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**</span></span> |
| <span data-ttu-id="fb169-399">/REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-399">/REPORTING_DB_NAME</span></span> | <span data-ttu-id="fb169-400">指定應該建立的新報表資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-400">Specifies the name of the new Reporting database that should be created.</span></span> <span data-ttu-id="fb169-401">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-401">Takes a string.</span></span> <span data-ttu-id="fb169-402">範例用法： **/REPORTING_DB_NAME = "AppVMgmtDB"**</span><span class="sxs-lookup"><span data-stu-id="fb169-402">Example usage: **/REPORTING_DB_NAME="AppVMgmtDB"**</span></span> |
| <span data-ttu-id="fb169-403">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-403">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span> | <span data-ttu-id="fb169-404">表示將存取資料庫的報表伺服器已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fb169-404">Indicates that the Reporting server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="fb169-405">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-405">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="fb169-406">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-406">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span> | <span data-ttu-id="fb169-407">指定要安裝報表伺服器的遠端電腦的電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb169-407">Specifies the machine account of the remote machine that the Reporting server will be installed on.</span></span> <span data-ttu-id="fb169-408">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-408">Takes a string.</span></span> <span data-ttu-id="fb169-409">範例用法： **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"**</span><span class="sxs-lookup"><span data-stu-id="fb169-409">Example usage: **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="domain\computername"**</span></span> |
| <span data-ttu-id="fb169-410">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="fb169-410">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span> | <span data-ttu-id="fb169-411">表示將用於安裝 App-v 報表服務器的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="fb169-411">Indicates the Administrator account that will be used to install the App-V Reporting Server.</span></span> <span data-ttu-id="fb169-412">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-412">Takes a string.</span></span> <span data-ttu-id="fb169-413">範例用法： **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"**</span><span class="sxs-lookup"><span data-stu-id="fb169-413">Example usage: **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="domain\\alias"**</span></span> |

#### <span data-ttu-id="fb169-414">使用現有管理伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="fb169-414">Parameters for using an existing Management Server Database</span></span>

| <span data-ttu-id="fb169-415">參數</span><span class="sxs-lookup"><span data-stu-id="fb169-415">Parameter</span></span> | <span data-ttu-id="fb169-416">資訊</span><span class="sxs-lookup"><span data-stu-id="fb169-416">Information</span></span> |
|--|--|
| <span data-ttu-id="fb169-417">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="fb169-417">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span> | <span data-ttu-id="fb169-418">表示 SQL Server 已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fb169-418">Indicates that the SQL Server is installed on the local server.</span></span> <span data-ttu-id="fb169-419">Switch 參數，因此不需要任何值。如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-419">Switch parameter so no value is expected.If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="fb169-420">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-420">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span> | <span data-ttu-id="fb169-421">指定安裝 SQL Server 之遠端電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-421">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="fb169-422">接受字串。</span><span class="sxs-lookup"><span data-stu-id="fb169-422">Takes a string.</span></span> <span data-ttu-id="fb169-423">範例用法： **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"**</span><span class="sxs-lookup"><span data-stu-id="fb169-423">Example usage: **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME="mycomputer1"**</span></span> |
| <span data-ttu-id="fb169-424">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fb169-424">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="fb169-425">表示要使用預設的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="fb169-425">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="fb169-426">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="fb169-426">Switch parameter so no value is expected.</span></span> <span data-ttu-id="fb169-427">如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-427">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="fb169-428">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="fb169-428">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="fb169-429">指定將使用之自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-429">Specifies the name of the custom SQL instance that will be used.</span></span> <span data-ttu-id="fb169-430">範例用法 **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement"**。</span><span class="sxs-lookup"><span data-stu-id="fb169-430">Example usage **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE="AppVManagement"**.</span></span> <span data-ttu-id="fb169-431">如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-431">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="fb169-432">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="fb169-432">/EXISTING_MANAGEMENT_DB_NAME</span></span> | <span data-ttu-id="fb169-433">指定應該使用之現有管理資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb169-433">Specifies the name of the existing management database that should be used.</span></span> <span data-ttu-id="fb169-434">範例用法： **/EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB"**。</span><span class="sxs-lookup"><span data-stu-id="fb169-434">Example usage: **/EXISTING_MANAGEMENT_DB_NAME="AppVMgmtDB"**.</span></span> <span data-ttu-id="fb169-435">如果已指定 **/DB_PREDEPLOY_MANAGEMENT** ，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="fb169-435">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |

<span data-ttu-id="fb169-436">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="fb169-436">Got an App-V issue?</span></span> <span data-ttu-id="fb169-437">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="fb169-437">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="fb169-438">相關主題</span><span class="sxs-lookup"><span data-stu-id="fb169-438">Related topics</span></span>

[<span data-ttu-id="fb169-439">部署 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="fb169-439">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)
