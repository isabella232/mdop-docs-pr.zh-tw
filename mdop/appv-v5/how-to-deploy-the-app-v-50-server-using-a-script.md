---
title: 如何使用指令碼來部署 App-V 5.0 伺服器
description: 如何使用指令碼來部署 App-V 5.0 伺服器
author: dansimp
ms.assetid: b91a35c8-df9e-4065-9187-abafbe565b84
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: aeb16d166fe7b1c4bb418c212024c49f6b151b94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800526"
---
# <span data-ttu-id="1bb8c-103">如何使用指令碼來部署 App-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="1bb8c-103">How to Deploy the App-V 5.0 Server Using a Script</span></span>


<span data-ttu-id="1bb8c-104">若要使用命令列成功完成**appv\_server\_setup.exe**伺服器設定，您必須指定併合並多個參數。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-104">In order to complete the **appv\_server\_setup.exe** Server setup successfully using the command line, you must specify and combine multiple parameters.</span></span>

<span data-ttu-id="1bb8c-105">如需使用命令列安裝 App-v 5.0 伺服器的詳細資訊，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-105">Use the following tables for more information about installing the App-V 5.0 server using the command line.</span></span>

>[!NOTE]
> <span data-ttu-id="1bb8c-106">您也可以在命令列中輸入下列命令，以存取下清單格中的資訊：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-106">The information in the following tables can also be accessed using the command line by typing the following command:</span></span>
>```
> appv\_server\_setup.exe /?
>```

## <span data-ttu-id="1bb8c-107">常見參數和範例</span><span class="sxs-lookup"><span data-stu-id="1bb8c-107">Common parameters and Examples</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-108">在本機電腦上安裝管理伺服器與管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-108">To Install the Management server and Management database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-109">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-109">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-110">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-110">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-111">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-111">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-112">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-112">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-113">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-113">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-114">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-114">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-116">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-116">/MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-117">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-117">To use a custom instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-118">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-118">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-119">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-119">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-120">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-120">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-121">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-121">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-122">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-122">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-123">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-123">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-124">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-124">/MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-125">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-125">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-126">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-126">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-127">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-127">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="1bb8c-128">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-128">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="1bb8c-129">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-129">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="1bb8c-130">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-130">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="1bb8c-131">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-131">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="1bb8c-132">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-132">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-133">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-133">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>
     
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-134">在本機電腦上使用現有的管理資料庫來安裝管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-134">To Install the Management server using an existing Management database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-135">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-135">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-136">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-136">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-137">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-137">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-138">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-138">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-139">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-139">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-140">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-140">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-141">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-141">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-142">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-142">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-143">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-143">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-144">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-144">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-145">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-145">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-146">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-146">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-147">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-147">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-148">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-148">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-149">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-149">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-150">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-150">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-151">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-151">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-152">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-152">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-153">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-153">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="1bb8c-154">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-154">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="1bb8c-155">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-155">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="1bb8c-156">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-156">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="1bb8c-157">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-157">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="1bb8c-158">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-158">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE =”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-159">/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-159">/EXISTING_MANAGEMENT_DB_NAME =”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>  

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-160">使用遠端電腦上現有的管理資料庫來安裝管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-160">To install the Management server using an existing Management database on a remote machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-161">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-161">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-162">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-162">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-163">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-163">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-164">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-164">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-165">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-165">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-166">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-166">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-167">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-167">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-168">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-168">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-169">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-169">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-170">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-170">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-171">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-171">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-172">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-172">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-173">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-173">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-174">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-174">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-175">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-175">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-176">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-176">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-177">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-177">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-178">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-178">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-179">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-179">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="1bb8c-180">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-180">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="1bb8c-181">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-181">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="1bb8c-182">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-182">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="1bb8c-183">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME = "SqlServermachine"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-183">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME=”SqlServermachine.domainName”</span></span></p>
    <p><span data-ttu-id="1bb8c-184">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-184">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE =”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-185">/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-185">/EXISTING_MANAGEMENT_DB_NAME =”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-186">在同一部電腦上安裝管理資料庫和管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-186">To Install the Management database and the Management Server on the same computer.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-187">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-187">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-188">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-188">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-189">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-189">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-190">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-190">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-191">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-191">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-192">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-192">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-193">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-193">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-194">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-194">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-195">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-195">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-196">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-196">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-197">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-197">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-198">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-198">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-199">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-199">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-200">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-200">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-201">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-201">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="1bb8c-202">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-202">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-203">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-203">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p>
    <p><span data-ttu-id="1bb8c-204">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-204">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="1bb8c-205">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-205">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-206">若要在與管理伺服器不同的電腦上安裝管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-206">To install the Management database on a different computer than the Management server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-207">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-207">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-208">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-208">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-209">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-209">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-210">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-210">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-211">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-211">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-212">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-212">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-213">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-213">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-214">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-214">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-215">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-215">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-216">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-216">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-217">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-217">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-218">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-218">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-219">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-219">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-220">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-220">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-221">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-221">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="1bb8c-222">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-222">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-223">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-223">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p>
    <p><span data-ttu-id="1bb8c-224">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "Domain\MachineAccount"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-224">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT=”Domain\MachineAccount”</span></span></p>
    <p><span data-ttu-id="1bb8c-225">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-225">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-226">以安裝發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-226">To Install the publishing server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-227">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-227">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-228">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-228">/PUBLISHING_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-229">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-229">/PUBLISHING_MGT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-230">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-230">/PUBLISHING_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-231">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-231">/PUBLISHING_WEBSITE_PORT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-232">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-232">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-233">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-233">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-234">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-234">/PUBLISHING_SERVER</span></span></p>
    <p><span data-ttu-id="1bb8c-235">/PUBLISHING_MGT_SERVER = " http://ManagementServerName:ManagementPort "</span><span class="sxs-lookup"><span data-stu-id="1bb8c-235">/PUBLISHING_MGT_SERVER=”http://ManagementServerName:ManagementPort”</span></span></p>
    <p><span data-ttu-id="1bb8c-236">/PUBLISHING_WEBSITE_NAME = "Microsoft AppV 發佈服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-236">/PUBLISHING_WEBSITE_NAME=”Microsoft AppV Publishing Service”</span></span></p>
    <p><span data-ttu-id="1bb8c-237">/PUBLISHING_WEBSITE_PORT = "8081"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-237">/PUBLISHING_WEBSITE_PORT=”8081”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-238">在本機電腦上安裝報表伺服器與報告資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-238">To Install the Reporting server and Reporting database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-239">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-239">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-240">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-240">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-241">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-241">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-242">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-242">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-243">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-243">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-244">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-244">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-245">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-245">/REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-246">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-246">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-247">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-247">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-248">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-248">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-249">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-249">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-250">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-250">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-251">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-251">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-252">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-252">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-253">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-253">/REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-254">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-254">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-255">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-255">/appv_server_setup.exe /QUIET</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-256">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-256">/REPORTING_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-257">/REPORTING_WEBSITE_NAME = "Microsoft AppV 報表服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-257">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-258">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-258">/REPORTING_WEBSITE_PORT=”8082”</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-259">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-259">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-260">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-260">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-261">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-261">/REPORTING_DB_NAME=”AppVReporting”</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-262">在本機電腦上安裝報表伺服器並使用現有的報表資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-262">To Install the Reporting server and using an existing Reporting database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-263">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-263">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-264">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-264">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-265">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-265">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-266">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-266">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-267">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-267">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-268">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-268">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-269">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-269">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-270">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-270">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-271">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-271">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-272">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-272">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-273">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-273">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-274">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-274">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-275">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-275">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-276">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-276">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-277">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-277">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-278">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-278">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-279">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-279">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-280">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-280">/REPORTING_SERVER</span></span></p>
    <p><span data-ttu-id="1bb8c-281">/REPORTING_WEBSITE_NAME = "Microsoft AppV 報表服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-281">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p>
    <p><span data-ttu-id="1bb8c-282">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-282">/REPORTING_WEBSITE_PORT=”8082”</span></span></p>
    <p><span data-ttu-id="1bb8c-283">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-283">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="1bb8c-284">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-284">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-285">/EXITING_REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-285">/EXITING_REPORTING_DB_NAME=”AppVReporting”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-286">使用遠端電腦上現有的報表資料庫來安裝報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-286">To Install the Reporting server using an existing Reporting database on a remote machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-287">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-287">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-288">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-288">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-289">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-289">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-290">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-290">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-291">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-291">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-292">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-292">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-293">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-293">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-294">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-294">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-295">/REPORTING _SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-295">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-296">/REPORTING _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-296">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-297">/REPORTING _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-297">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-298">/REPORTING _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-298">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-299">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-299">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-300">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-300">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-301">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-301">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-302">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-302">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-303">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-303">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-304">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-304">/REPORTING_SERVER</span></span></p>
    <p><span data-ttu-id="1bb8c-305">/REPORTING_WEBSITE_NAME = "Microsoft AppV 報表服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-305">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p>
    <p><span data-ttu-id="1bb8c-306">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-306">/REPORTING_WEBSITE_PORT=”8082”</span></span></p>
    <p><span data-ttu-id="1bb8c-307">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME = "SqlServerMachine"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-307">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME=”SqlServerMachine.DomainName”</span></span></p>
    <p><span data-ttu-id="1bb8c-308">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-308">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-309">/EXITING_REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-309">/EXITING_REPORTING_DB_NAME=”AppVReporting”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-310">在與報表伺服器相同的電腦上安裝報表資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-310">To install the Reporting database on the same computer as the Reporting server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-311">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-311">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-312">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-312">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-313">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-313">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-314">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-314">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-315">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-315">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-316">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-316">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-317">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-317">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-318">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-318">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-319">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-319">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-320">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-320">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-321">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-321">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-322">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-322">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-323">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-323">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-324">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-324">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-325">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-325">/DB_PREDEPLOY_REPORTING</span></span></p>
    <p><span data-ttu-id="1bb8c-326">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-326">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-327">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-327">/REPORTING_DB_NAME=”AppVReporting”</span></span></p>
    <p><span data-ttu-id="1bb8c-328">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-328">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="1bb8c-329">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-329">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-330">在不同的電腦上安裝報表資料庫，而不是報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-330">To install the Reporting database on a different computer than the Reporting server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-331">若要使用 Microsoft SQL Server 的預設實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-331">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-332">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-332">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-333">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-333">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-334">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-334">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-335">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-335">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-336">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-336">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-337">若要使用 Microsoft SQL Server 的自訂實例，請使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-337">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="1bb8c-338">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-338">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-339">/REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-339">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-340">/REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-340">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-341">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-341">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="1bb8c-342">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-342">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="1bb8c-343">使用 Microsoft SQL Server 的自訂實例範例：</span><span class="sxs-lookup"><span data-stu-id="1bb8c-343">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="1bb8c-344">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-344">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="1bb8c-345">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-345">/DB_PREDEPLOY_REPORTING</span></span></p>
    <p><span data-ttu-id="1bb8c-346">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-346">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="1bb8c-347">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-347">/REPORTING_DB_NAME=”AppVReporting”</span></span></p>
    <p><span data-ttu-id="1bb8c-348">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "Domain\MachineAccount"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-348">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT=”Domain\MachineAccount”</span></span></p>
    <p><span data-ttu-id="1bb8c-349">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-349">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

## <span data-ttu-id="1bb8c-350">參數定義</span><span class="sxs-lookup"><span data-stu-id="1bb8c-350">Parameter Definitions</span></span>

### <span data-ttu-id="1bb8c-351">一般參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-351">General Parameters</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-352">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-352">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-353">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-353">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-354">/QUIET</span><span class="sxs-lookup"><span data-stu-id="1bb8c-354">/QUIET</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-355">指定 [緘默安裝]。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-355">Specifies silent install.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-356">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-356">/UNINSTALL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-357">指定卸載。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-357">Specifies an uninstall.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-358">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-358">/LAYOUT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-359">指定 [版面配置] 動作。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-359">Specifies layout action.</span></span> <span data-ttu-id="1bb8c-360">這會將 MSIs 和腳本檔案解壓縮至資料夾，而不會實際安裝產品。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-360">This extracts the MSIs and script files to a folder without actually installing the product.</span></span> <span data-ttu-id="1bb8c-361">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-361">No value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-362">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="1bb8c-362">/LAYOUTDIR</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-363">指定版面配置目錄。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-363">Specifies the layout directory.</span></span> <span data-ttu-id="1bb8c-364">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-364">Takes a string.</span></span> <span data-ttu-id="1bb8c-365">例如，/LAYOUTDIR = "C:\Application Virtualization 伺服器"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-365">For example, /LAYOUTDIR=”C:\Application Virtualization Server”</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-366">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="1bb8c-366">/INSTALLDIR</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-367">指定安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-367">Specifies the installation directory.</span></span> <span data-ttu-id="1bb8c-368">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-368">Takes a string.</span></span> <span data-ttu-id="1bb8c-369">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-369">E.g.</span></span> <span data-ttu-id="1bb8c-370">/INSTALLDIR = "C:\Program Files\Application Virtualization\Server"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-370">/INSTALLDIR=”C:\Program Files\Application Virtualization\Server”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-371">/MUOPTIN</span><span class="sxs-lookup"><span data-stu-id="1bb8c-371">/MUOPTIN</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-372">啟用 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-372">Enables Microsoft Update.</span></span> <span data-ttu-id="1bb8c-373">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="1bb8c-373">No value is expected</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-374">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="1bb8c-374">/ACCEPTEULA</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-375">接受授權合約。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-375">Accepts the license agreement.</span></span> <span data-ttu-id="1bb8c-376">這對於無操作安裝是必要的。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-376">This is required for an unattended installation.</span></span> <span data-ttu-id="1bb8c-377">範例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-377">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="1bb8c-378">管理伺服器安裝參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-378">Management Server Installation Parameters</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-379">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-379">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-380">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-380">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-381">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-381">/MANAGEMENT_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-382">指定將安裝管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-382">Specifies that the management server will be installed.</span></span> <span data-ttu-id="1bb8c-383">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="1bb8c-383">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-384">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-384">/MANAGEMENT_ADMINACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-385">指定允許系統管理員存取管理伺服器的帳戶：此帳戶可以是個別的使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-385">Specifies the account that will be allowed to Administrator access to the management server This account can be an individual user account or a group.</span></span> <span data-ttu-id="1bb8c-386">範例用法： <strong> /MANAGEMENT_ADMINACCOUNT = "mydomain\admin" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-386">Example usage: <strong>/MANAGEMENT_ADMINACCOUNT=”mydomain\admin”</strong>.</span></span> <span data-ttu-id="1bb8c-387">如果 <strong> </strong> 未指定/MANAGEMENT_SERVER，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-387">If <strong>/MANAGEMENT_SERVER</strong> is not specified, this will be ignored.</span></span> <span data-ttu-id="1bb8c-388">指定允許系統管理員存取管理伺服器的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-388">Specifies the account that will be allowed to Administrator access to the management server.</span></span> <span data-ttu-id="1bb8c-389">這可以是使用者帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-389">This can be a user account or a group.</span></span> <span data-ttu-id="1bb8c-390">例如， <strong> /MANAGEMENT_ADMINACCOUNT = &quot; mydomain\admin &quot; </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-390">For example, <strong>/MANAGEMENT_ADMINACCOUNT=&quot;mydomain\admin&quot;</strong>.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-391">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-391">/MANAGEMENT_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-392">指定將為管理服務建立的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-392">Specifies name of the website that will be created for the management service.</span></span> <span data-ttu-id="1bb8c-393">例如，/MANAGEMENT_WEBSITE_NAME = "Microsoft App-v Management Service"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-393">For example, /MANAGEMENT_WEBSITE_NAME=”Microsoft App-V Management Service”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-394">MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-394">MANAGEMENT_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-395">指定管理服務將使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-395">Specifies the port number that will be used by the management service will use.</span></span> <span data-ttu-id="1bb8c-396">例如，/MANAGEMENT_WEBSITE_PORT = 82。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-396">For example, /MANAGEMENT_WEBSITE_PORT=82.</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="1bb8c-397">管理伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-397">Parameters for the Management Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-398">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-398">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-399">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-399">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-400">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-400">/DB_PREDEPLOY_MANAGEMENT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-401">指定將安裝管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-401">Specifies that the management database will be installed.</span></span> <span data-ttu-id="1bb8c-402">您必須具備足夠的資料庫許可權，才能完成此安裝。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-402">You must have sufficient database permissions to complete this installation.</span></span> <span data-ttu-id="1bb8c-403">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="1bb8c-403">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-404">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-404">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-405">表示應該使用預設的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-405">Indicates that the default SQL instance should be used.</span></span> <span data-ttu-id="1bb8c-406">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-406">No value is expected.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-407">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-407">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-408">指定應該用來建立新資料庫的自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-408">Specifies the name of the custom SQL instance that should be used to create a new database.</span></span> <span data-ttu-id="1bb8c-409">範例用法： <strong> /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-409">Example usage: <strong>/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE=”MYSQLSERVER”</strong>.</span></span> <span data-ttu-id="1bb8c-410">如果未指定/DB_PREDEPLOY_MANAGEMENT，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-410">If /DB_PREDEPLOY_MANAGEMENT is not specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-411">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-411">/MANAGEMENT_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-412">指定應該建立的新管理資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-412">Specifies the name of the new management database that should be created.</span></span> <span data-ttu-id="1bb8c-413">範例用法： <strong> /MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-413">Example usage: <strong>/MANAGEMENT_DB_NAME=”AppVMgmtDB”</strong>.</span></span> <span data-ttu-id="1bb8c-414">如果未指定/DB_PREDEPLOY_MANAGEMENT，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-414">If /DB_PREDEPLOY_MANAGEMENT is not specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-415">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-415">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-416">指明將存取資料庫的管理伺服器是否已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-416">Indicates if the management server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="1bb8c-417">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-417">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-418">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-418">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-419">指定將安裝管理伺服器的遠端電腦的電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-419">Specifies the machine account of the remote machine that the management server will be installed on.</span></span> <span data-ttu-id="1bb8c-420">範例用法： <strong> /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-420">Example usage: <strong>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT=”domain\computername”</span></span></strong></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-421">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-421">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-422">表示將用於安裝管理伺服器的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-422">Indicates the Administrator account that will be used to install the management server.</span></span> <span data-ttu-id="1bb8c-423">範例用法： <strong> /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\alias"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-423">Example usage: <strong>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT =”domain\alias”</span></span></strong></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="1bb8c-424">安裝發佈伺服器的參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-424">Parameters for Installing Publishing Server</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-425">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-425">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-426">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-426">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-427">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-427">/PUBLISHING_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-428">指定將安裝發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-428">Specifies that the Publishing Server will be installed.</span></span> <span data-ttu-id="1bb8c-429">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="1bb8c-429">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-430">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-430">/PUBLISHING_MGT_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-431">指定發佈伺服器將連接的管理服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-431">Specifies the URL to Management Service the Publishing server will connect to.</span></span> <span data-ttu-id="1bb8c-432">範例用法： <strong> HTTP:// &lt; 管理伺服器名稱 &gt; ： &lt; 管理伺服器埠號碼 &gt; </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-432">Example usage: <strong>http://&lt;management server name&gt;:&lt;Management server port number&gt;</strong>.</span></span> <span data-ttu-id="1bb8c-433">如果未使用/PUBLISHING_SERVER，則會忽略此參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-433">If /PUBLISHING_SERVER is not used, this parameter will be ignored</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-434">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-434">/PUBLISHING_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-435">指定要針對發佈服務建立的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-435">Specifies name of the website that will be created for the publishing service.</span></span> <span data-ttu-id="1bb8c-436">例如，/PUBLISHING_WEBSITE_NAME = "Microsoft App-v 發佈服務"</span><span class="sxs-lookup"><span data-stu-id="1bb8c-436">For example, /PUBLISHING_WEBSITE_NAME=”Microsoft App-V Publishing Service”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-437">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-437">/PUBLISHING_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-438">指定發佈服務所使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-438">Specifies the port number used by the publishing service.</span></span> <span data-ttu-id="1bb8c-439">例如，/PUBLISHING_WEBSITE_PORT = 83</span><span class="sxs-lookup"><span data-stu-id="1bb8c-439">For example, /PUBLISHING_WEBSITE_PORT=83</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="1bb8c-440">報表伺服器的參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-440">Parameters for Reporting Server</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-441">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-441">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-442">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-442">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-443">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="1bb8c-443">/REPORTING_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-444">指定將安裝報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-444">Specifies that the Reporting Server will be installed.</span></span> <span data-ttu-id="1bb8c-445">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="1bb8c-445">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-446">/REPORTING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-446">/REPORTING_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-447">指定要為報表服務建立的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-447">Specifies name of the website that will be created for the Reporting Service.</span></span> <span data-ttu-id="1bb8c-448">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-448">E.g.</span></span> <span data-ttu-id="1bb8c-449">/REPORTING_WEBSITE_NAME = &quot; Microsoft App-v ReportingService&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-449">/REPORTING_WEBSITE_NAME=&quot;Microsoft App-V ReportingService&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-450">/REPORTING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-450">/REPORTING_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-451">指定報表服務將使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-451">Specifies the port number that the Reporting Service will use.</span></span> <span data-ttu-id="1bb8c-452">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-452">E.g.</span></span> <span data-ttu-id="1bb8c-453">/REPORTING_WEBSITE_PORT = 82</span><span class="sxs-lookup"><span data-stu-id="1bb8c-453">/REPORTING_WEBSITE_PORT=82</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

### <span data-ttu-id="1bb8c-454">使用現有報表伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-454">Parameters for using an Existing Reporting Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-455">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-455">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-456">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-456">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-457">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-457">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-458">表示 Microsoft SQL Server 已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-458">Indicates that the Microsoft SQL Server is installed on the local server.</span></span> <span data-ttu-id="1bb8c-459">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-459">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-460">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-460">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-461">指定安裝 SQL Server 之遠端電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-461">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="1bb8c-462">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-462">Takes a string.</span></span> <span data-ttu-id="1bb8c-463">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-463">E.g.</span></span> <span data-ttu-id="1bb8c-464">/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-464">/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME=&quot;mycomputer1&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-465">/EXISTING_ 報告 <em> DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-465">/EXISTING_ REPORTING <em>DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-466">表示要使用預設的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-466">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="1bb8c-467">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-467">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-468">/EXISTING </em> REPORTING_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-468">/EXISTING</em> REPORTING_DB_CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-469">指定應該使用的自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-469">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="1bb8c-470">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-470">Takes a string.</span></span> <span data-ttu-id="1bb8c-471">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-471">E.g.</span></span> <span data-ttu-id="1bb8c-472">/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-472">/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE=&quot;MYSQLSERVER&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-473">/EXISTING_ 報告 _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-473">/EXISTING_ REPORTING _DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-474">指定應該使用之現有報表資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-474">Specifies the name of the existing Reporting database that should be used.</span></span> <span data-ttu-id="1bb8c-475">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-475">Takes a string.</span></span> <span data-ttu-id="1bb8c-476">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-476">E.g.</span></span> <span data-ttu-id="1bb8c-477">/EXISTING_REPORTING_DB_NAME = &quot; AppVReporting&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-477">/EXISTING_REPORTING_DB_NAME=&quot;AppVReporting&quot;</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="1bb8c-478">安裝報表伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-478">Parameters for installing Reporting Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-479">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-479">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-480">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-480">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-481">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="1bb8c-481">/DB_PREDEPLOY_REPORTING</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-482">指定將安裝報表資料庫。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-482">Specifies that the Reporting Database will be installed.</span></span> <span data-ttu-id="1bb8c-483">此安裝需要擁有 DBA 許可權。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-483">DBA permissions are required for this installation.</span></span> <span data-ttu-id="1bb8c-484">不需要任何值</span><span class="sxs-lookup"><span data-stu-id="1bb8c-484">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-485">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-485">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-486">指定應該使用的自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-486">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="1bb8c-487">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-487">Takes a string.</span></span> <span data-ttu-id="1bb8c-488">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-488">E.g.</span></span> <span data-ttu-id="1bb8c-489">/REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-489">/REPORTING_DB_ CUSTOM_SQLINSTANCE=&quot;MYSQLSERVER&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-490">/REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-490">/REPORTING_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-491">指定應該建立的新報表資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-491">Specifies the name of the new Reporting database that should be created.</span></span> <span data-ttu-id="1bb8c-492">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-492">Takes a string.</span></span> <span data-ttu-id="1bb8c-493">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-493">E.g.</span></span> <span data-ttu-id="1bb8c-494">/REPORTING_DB_NAME = &quot; AppVMgmtDB&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-494">/REPORTING_DB_NAME=&quot;AppVMgmtDB&quot;</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-495">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-495">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-496">表示將存取資料庫的報表伺服器已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-496">Indicates that the Reporting server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="1bb8c-497">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-497">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-498">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-498">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-499">指定要安裝報表伺服器的遠端電腦的電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-499">Specifies the machine account of the remote machine that the Reporting server will be installed on.</span></span> <span data-ttu-id="1bb8c-500">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-500">Takes a string.</span></span> <span data-ttu-id="1bb8c-501">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-501">E.g.</span></span> <span data-ttu-id="1bb8c-502">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot; domain\computername&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-502">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot;domain\computername&quot;</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-503">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-503">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-504">表示將用於安裝 App-v 報表服務器的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-504">Indicates the Administrator account that will be used to install the App-V Reporting Server.</span></span> <span data-ttu-id="1bb8c-505">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-505">Takes a string.</span></span> <span data-ttu-id="1bb8c-506">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-506">E.g.</span></span> <span data-ttu-id="1bb8c-507">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot; domain\alias&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-507">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot;domain\alias&quot;</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="1bb8c-508">使用現有管理伺服器資料庫的參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-508">Parameters for using an existing Management Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="1bb8c-509">參數</span><span class="sxs-lookup"><span data-stu-id="1bb8c-509">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="1bb8c-510">資訊</span><span class="sxs-lookup"><span data-stu-id="1bb8c-510">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-511">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1bb8c-511">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-512">表示 SQL Server 已安裝在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-512">Indicates that the SQL Server is installed on the local server.</span></span> <span data-ttu-id="1bb8c-513">Switch 參數，因此不需要任何值。如果已指定/DB_PREDEPLOY_MANAGEMENT，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-513">Switch parameter so no value is expected.If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-514">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-514">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-515">指定安裝 SQL Server 之遠端電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-515">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="1bb8c-516">接受字串。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-516">Takes a string.</span></span> <span data-ttu-id="1bb8c-517">例如</span><span class="sxs-lookup"><span data-stu-id="1bb8c-517">E.g.</span></span> <span data-ttu-id="1bb8c-518">/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</span><span class="sxs-lookup"><span data-stu-id="1bb8c-518">/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME=&quot;mycomputer1&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-519">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1bb8c-519">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-520">表示要使用預設的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-520">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="1bb8c-521">Switch 參數，因此不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-521">Switch parameter so no value is expected.</span></span> <span data-ttu-id="1bb8c-522">如果已指定/DB_PREDEPLOY_MANAGEMENT，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-522">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="1bb8c-523">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="1bb8c-523">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-524">指定將使用之自訂 SQL 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-524">Specifies the name of the custom SQL instance that will be used.</span></span> <span data-ttu-id="1bb8c-525">範例用法 <strong> /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-525">Example usage <strong>/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE=”AppVManagement”</strong>.</span></span> <span data-ttu-id="1bb8c-526">如果已指定/DB_PREDEPLOY_MANAGEMENT，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-526">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="1bb8c-527">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1bb8c-527">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="1bb8c-528">指定應該使用之現有管理資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-528">Specifies the name of the existing management database that should be used.</span></span> <span data-ttu-id="1bb8c-529">範例用法： <strong> /EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-529">Example usage: <strong>/EXISTING_MANAGEMENT_DB_NAME=”AppVMgmtDB”</strong>.</span></span> <span data-ttu-id="1bb8c-530">如果已指定/DB_PREDEPLOY_MANAGEMENT，將會忽略此情況。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-530">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p>
    <p></p>
    <p><strong><span data-ttu-id="1bb8c-531">您有應用程式-V 的建議 </strong> 嗎？</span><span class="sxs-lookup"><span data-stu-id="1bb8c-531">Got a suggestion for App-V</strong>?</span></span> <span data-ttu-id="1bb8c-532">在此新增或投票 <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)"> 建議 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-532">Add or vote on suggestions <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)">here</a>.</span></span> <strong><span data-ttu-id="1bb8c-533">您有 App-v issu </strong> e？</span><span class="sxs-lookup"><span data-stu-id="1bb8c-533">Got an App-V issu</strong>e?</span></span> <span data-ttu-id="1bb8c-534">使用 <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)"> App-v TechNet 論壇 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1bb8c-534">Use the <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)">App-V TechNet Forum</a>.</span></span></p></td>
</tr>
</tbody>
</table>
  

## <span data-ttu-id="1bb8c-535">相關主題</span><span class="sxs-lookup"><span data-stu-id="1bb8c-535">Related topics</span></span>

[<span data-ttu-id="1bb8c-536">部署 App-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="1bb8c-536">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

 

 





