---
title: 如何使用 SQL 指令碼部署 App-V 資料庫
description: 如何使用 SQL 指令碼部署 App-V 資料庫
author: dansimp
ms.assetid: 23637936-475f-4ca5-adde-76bb27d2372b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 511d1020571eead25af9e9591fe1834a9f97f068
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800512"
---
# <span data-ttu-id="1b9bd-103">如何使用 SQL 指令碼部署 App-V 資料庫</span><span class="sxs-lookup"><span data-stu-id="1b9bd-103">How to Deploy the App-V Databases by Using SQL Scripts</span></span>


<span data-ttu-id="1b9bd-104">使用下列指示來使用 SQL 腳本（而不是 Windows 安裝程式）來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="1b9bd-104">Use the following instructions to use SQL scripts, rather than the Windows Installer, to:</span></span>

-   <span data-ttu-id="1b9bd-105">安裝 App-v 5.0 資料庫</span><span class="sxs-lookup"><span data-stu-id="1b9bd-105">Install the App-V 5.0 databases</span></span>

-   <span data-ttu-id="1b9bd-106">將5.0 資料庫升級為較新的版本</span><span class="sxs-lookup"><span data-stu-id="1b9bd-106">Upgrade the 5.0 databases to a later version</span></span>

**<span data-ttu-id="1b9bd-107">如何使用 SQL 腳本來安裝 App-v 資料庫</span><span class="sxs-lookup"><span data-stu-id="1b9bd-107">How to install the App-V databases by using SQL scripts</span></span>**

1. <span data-ttu-id="1b9bd-108">在您安裝資料庫腳本之前，請先查看並保留 App-v 授權條款的複本。</span><span class="sxs-lookup"><span data-stu-id="1b9bd-108">Before you install the database scripts, review and keep a copy of the App-V license terms.</span></span> <span data-ttu-id="1b9bd-109">透過執行資料庫腳本，您即已同意授權條款。</span><span class="sxs-lookup"><span data-stu-id="1b9bd-109">By running the database scripts, you are agreeing to the license terms.</span></span> <span data-ttu-id="1b9bd-110">如果您不接受，請不要使用這個軟體。</span><span class="sxs-lookup"><span data-stu-id="1b9bd-110">If you do not accept them, you should not use this software.</span></span>

2. <span data-ttu-id="1b9bd-111">將**appv\_server\_setup.exe**從 app-v 版本媒體複製到臨時位置。</span><span class="sxs-lookup"><span data-stu-id="1b9bd-111">Copy the **appv\_server\_setup.exe** from the App-V release media to a temporary location.</span></span>

3. <span data-ttu-id="1b9bd-112">從命令提示字元執行**appv\_server\_setup.exe** ，並指定解壓縮資料庫腳本的臨時位置。</span><span class="sxs-lookup"><span data-stu-id="1b9bd-112">From a command prompt, run **appv\_server\_setup.exe** and specify a temporary location for extracting the database scripts.</span></span>

   <span data-ttu-id="1b9bd-113">範例： appv\_server\_setup.exe/layout c:\\ &lt; 臨時位置路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="1b9bd-113">Example: appv\_server\_setup.exe /layout c:\\&lt;temporary location path&gt;</span></span>

4. <span data-ttu-id="1b9bd-114">流覽至您建立的臨時位置，開啟 [提取的**DatabaseScripts** ] 資料夾，然後查看適當的 Readme.txt 檔案以取得相關指示：</span><span class="sxs-lookup"><span data-stu-id="1b9bd-114">Browse to the temporary location that you created, open the extracted **DatabaseScripts** folder, and review the appropriate Readme.txt file for instructions:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="1b9bd-115">資料庫</span><span class="sxs-lookup"><span data-stu-id="1b9bd-115">Database</span></span></th>
   <th align="left"><span data-ttu-id="1b9bd-116">要使用 Readme.txt 檔案的位置</span><span class="sxs-lookup"><span data-stu-id="1b9bd-116">Location of Readme.txt file to use</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="1b9bd-117">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="1b9bd-117">Management database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="1b9bd-118">ManagementDatabase 子資料夾</span><span class="sxs-lookup"><span data-stu-id="1b9bd-118">ManagementDatabase subfolder</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="1b9bd-119">重要</span><span class="sxs-lookup"><span data-stu-id="1b9bd-119">Important</span></span></strong><br/><p><span data-ttu-id="1b9bd-120">如果您要升級到或安裝應用程式-V 5.0 SP3 管理資料庫，請參閱 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安裝或升級 app-v 5.0 Sp3 管理伺服器資料庫的 SQL 腳本失敗 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1b9bd-120">If you are upgrading to or installing the App-V 5.0 SP3 Management database, see <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)">SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="1b9bd-121">報表資料庫</span><span class="sxs-lookup"><span data-stu-id="1b9bd-121">Reporting database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="1b9bd-122">ReportingDatabase 子資料夾</span><span class="sxs-lookup"><span data-stu-id="1b9bd-122">ReportingDatabase subfolder</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="1b9bd-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="1b9bd-123">Related topics</span></span>


[<span data-ttu-id="1b9bd-124">部署 App-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="1b9bd-124">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

[<span data-ttu-id="1b9bd-125">如何部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="1b9bd-125">How to Deploy the App-V 5.0 Server</span></span>](how-to-deploy-the-app-v-50-server-50sp3.md)









