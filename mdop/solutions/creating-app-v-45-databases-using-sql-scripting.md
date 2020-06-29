---
title: 使用 SQL 指令碼建立 APP-V 4.5 資料庫
description: 使用 SQL 指令碼建立 APP-V 4.5 資料庫
author: dansimp
ms.assetid: 6cd0b180-163e-463f-a658-939ab9a7cfa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ab2c102a43701bfdeaac49359b4ca3c4a063fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811480"
---
# <span data-ttu-id="a9ad2-103">使用 SQL 指令碼建立 APP-V 4.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="a9ad2-103">Creating App-V 4.5 Databases Using SQL Scripting</span></span>


**<span data-ttu-id="a9ad2-104">此解決方案的目的是誰？</span><span class="sxs-lookup"><span data-stu-id="a9ad2-104">Who is this solution intended for?</span></span>** <span data-ttu-id="a9ad2-105">管理應用程式虛擬化（App-v）4.5 資料庫的資訊技術專業人員。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-105">Information technology professionals who manage Application Virtualization (App-V) 4.5 databases.</span></span>

**<span data-ttu-id="a9ad2-106">本指南會如何協助您？</span><span class="sxs-lookup"><span data-stu-id="a9ad2-106">How can this guide help you?</span></span>** <span data-ttu-id="a9ad2-107">本方案說明如何在管理員安裝沒有 SQL Server 的「系統管理員」許可權的情況下，說明如何安裝 Microsoft Application Virtualization 伺服器的步驟。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-107">This solution explains and documents the procedure to install the Microsoft Application Virtualization Server when the administrator installing does not have “sysadmin” privileges to the SQL Server.</span></span>

## <span data-ttu-id="a9ad2-108">概觀</span><span class="sxs-lookup"><span data-stu-id="a9ad2-108">Overview</span></span>


<span data-ttu-id="a9ad2-109">安裝 Microsoft Application Virtualization 4.5 （App-v）的其中一個難題是，安裝程式假設安裝伺服器功能的使用者不僅是本機電腦系統管理員，還要擁有將裝載資料存放區之 SQL 伺服器的 SQL 系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-109">One of the challenges of installing Microsoft Application Virtualization 4.5 (App-V) is that the install program assumes that the user installing the server features will not only be a local computer administrator, but also have SQL administrator privileges on the SQL server that will host the Data Store.</span></span> <span data-ttu-id="a9ad2-110">這個需求是以資料庫及適當的角色和許可權，在安裝時建立的事實所依據。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-110">This requirement is based on the fact that the database, as well as the appropriate roles and permissions, are created as part of the install.</span></span> <span data-ttu-id="a9ad2-111">不過，在大部分的企業中，SQL server 會與將要安裝 App-v 的基礎結構小組分開管理。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-111">However, in most enterprises, SQL servers are managed separately from the infrastructure team who will be installing App-V.</span></span> <span data-ttu-id="a9ad2-112">這些安全需求將使 SQL 系統管理員難以取得安裝 app-v 的應用程式許可權;同樣地，SQL 系統管理員將沒有安裝產品以供基礎結構小組使用所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-112">These security requirements will make it difficult to get SQL administrators to give the infrastructure administrator installing App-V adequate rights; similarly, the SQL administrators will not have the required privileges to install the product for the infrastructure team.</span></span>

<span data-ttu-id="a9ad2-113">目前，試圖安裝 App-v 的管理員必須具備 SQL 「sysadmin」許可權。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-113">Currently, an administrator attempting the installation of App-V must have SQL “sysadmin” privileges.</span></span> <span data-ttu-id="a9ad2-114">在早期版本的產品中，SQL 系統管理員允許您建立暫時的「sysadmin」帳戶或在安裝期間出現，以提供「sysadmin」許可權的認證。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-114">In previous versions of the product the setup allowed for the SQL administrators to either create a temporary “sysadmin” account or be present during installation to provide credentials with “sysadmin” privileges.</span></span> <span data-ttu-id="a9ad2-115">在這個版本中，在發行的產品中提供腳本，供所有系統管理員在實施其基礎結構時使用。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-115">In this release, scripts are provided in the released product for all administrators to use when implementing their infrastructure.</span></span>

<span data-ttu-id="a9ad2-116">本白皮書將討論安裝需要劃分成兩個不同工作的案例：建立 SQL 資料庫，並安裝 App-v server 功能。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-116">This whitepaper discusses the scenario in which the install will need to be divided into two separate tasks: creating the SQL database, and installing the App-V server features.</span></span> <span data-ttu-id="a9ad2-117">SQL 系統管理員可以審查 SQL 腳本並進行修改，以解決與其他資料庫的任何衝突，或支援與其他工具的整合。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-117">The SQL administrators would be able to review the SQL scripts and make modifications to resolve any conflicts with other databases, or to support integration with other tools.</span></span> <span data-ttu-id="a9ad2-118">腳本的結果是允許 SQL 系統管理員準備資料庫，讓基礎結構系統管理員不需要授與 SQL server 的任何高級許可權。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-118">The result of the scripts is to allow SQL administrators to prepare the database so that the infrastructure administrators do not have to be granted any advanced rights on the SQL server.</span></span> <span data-ttu-id="a9ad2-119">在安全性原則會禁止此情況的環境中，這是很重要的。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-119">This is important in environments where security policies would prohibit this.</span></span>

### <span data-ttu-id="a9ad2-120">SQL 資料庫建立程式</span><span class="sxs-lookup"><span data-stu-id="a9ad2-120">SQL Database Creation Process</span></span>

<span data-ttu-id="a9ad2-121">SQL 腳本可讓 SQL 系統管理員建立必要的資料庫，同時也為 App-v 管理員設定許可權，以成功安裝及管理環境。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-121">The SQL scripts allow for SQL administrators to create the required database and also set up the privileges for the App-V administrators to successfully install and manage the environment.</span></span> <span data-ttu-id="a9ad2-122">本檔稍後會列出完成這些工作的步驟。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-122">The steps for completing these tasks are listed later in this document.</span></span>

<span data-ttu-id="a9ad2-123">這個程式會將資料庫建立與設定動作從實際的 App-v 安裝中分離。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-123">This process separates the database creation and configuration actions from the actual App-V installation.</span></span>

**<span data-ttu-id="a9ad2-124">要提供給 SQL 系統管理員的資訊</span><span class="sxs-lookup"><span data-stu-id="a9ad2-124">Information to be provided to SQL administrators</span></span>**

-   <span data-ttu-id="a9ad2-125">要成為應用程式 V 管理員的 AD 群組名稱</span><span class="sxs-lookup"><span data-stu-id="a9ad2-125">Name of AD group that is going to be the App-V admin’s</span></span>

-   <span data-ttu-id="a9ad2-126">將安裝 App-v 管理伺服器的伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="a9ad2-126">Name of the server where App-V Management Server will be installed</span></span>

**<span data-ttu-id="a9ad2-127">要傳回給基礎結構管理員的資訊</span><span class="sxs-lookup"><span data-stu-id="a9ad2-127">Information to be returned to the Infrastructure administrators</span></span>**

-   <span data-ttu-id="a9ad2-128">資料庫伺服器或實例的名稱與 App-v 資料庫的名稱</span><span class="sxs-lookup"><span data-stu-id="a9ad2-128">Name of the database server or instance and the name of the App-V database</span></span>

<span data-ttu-id="a9ad2-129">資料庫準備就緒之後，App-v 管理員就可以執行 App-v 安裝，而不需要 SQL 系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-129">Once the database has been prepared, the App-V administrators can run the App-V installation without SQL administrator privileges.</span></span>

### <span data-ttu-id="a9ad2-130">使用 SQL 安裝程式腳本</span><span class="sxs-lookup"><span data-stu-id="a9ad2-130">Using the SQL Setup Scripts</span></span>

**<span data-ttu-id="a9ad2-131">需求</span><span class="sxs-lookup"><span data-stu-id="a9ad2-131">Requirements</span></span>**

<span data-ttu-id="a9ad2-132">以下是使用位於選取的解壓位置根目錄之 support\\createdb 資料夾中的腳本需求清單。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-132">The following is a list of requirements for using the scripts which are located in the support\\createdb folder at the root of the selected extract location.</span></span>

-   <span data-ttu-id="a9ad2-133">必須將腳本複製到電腦上要執行的可寫位置（請務必在複製這些腳本後移除其唯讀屬性），而且必須在該電腦上載入 SQL 用戶端工具（osql 只需要在本機電腦上執行範例批次處理檔案）。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-133">Scripts must be copied to a writeable location on the computer where they will be run (be sure to remove the read only attribute from these scripts after they have been copied) and SQL client tools must be loaded on that computer (osql is only required for running the sample batch files on the local computer).</span></span>

-   <span data-ttu-id="a9ad2-134">SQL Server 必須支援 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-134">The SQL Server must support Windows Authentication.</span></span>

-   <span data-ttu-id="a9ad2-135">確認 SQL Server 實例與 SQL 代理服務正在執行。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-135">Ensure that the SQL Server Instance and SQL Agent Service are running.</span></span>

-   <span data-ttu-id="a9ad2-136">以 SQL 系統管理員（sysadmin）的網域帳戶登入，這些腳本將會在該電腦上完成。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-136">Log on with a domain account that is a SQL administrator (sysadmin) on the computer where the scripts will be done.</span></span>

<span data-ttu-id="a9ad2-137">腳本會在已登入的使用者網域認證下執行。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-137">The scripts runs under the logged-on user’s domain credentials.</span></span>

**<span data-ttu-id="a9ad2-138">使用 SQL 腳本建立資料庫</span><span class="sxs-lookup"><span data-stu-id="a9ad2-138">Database Creation Using SQL Scripts</span></span>**

**<span data-ttu-id="a9ad2-139">由 SQL 系統管理員執行的工作：</span><span class="sxs-lookup"><span data-stu-id="a9ad2-139">Tasks to be performed by SQL administrators:</span></span>**

1.  <span data-ttu-id="a9ad2-140">將 support\\createdb 資料夾中包含的腳本，從選取的解壓位置根目錄複寫到將執行腳本的電腦。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-140">Copy the scripts contained in the support\\createdb folder from the root of the selected extract location to the computer where the scripts will be run.</span></span> <span data-ttu-id="a9ad2-141">以下是腳本正常執行所需的檔案，且必須依下列順序進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-141">The following files are required for the scripts to run properly and must be called in the order presented below.</span></span>

    -   <span data-ttu-id="a9ad2-142">database .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-142">database.sql</span></span>

    -   <span data-ttu-id="a9ad2-143">roles. sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-143">roles.sql</span></span>

    -   <span data-ttu-id="a9ad2-144">表格 \ _CODES .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-144">table\_CODES.sql</span></span>

    -   <span data-ttu-id="a9ad2-145">函數 \ _before \ _tables .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-145">functions\_before\_tables.sql</span></span>

    -   <span data-ttu-id="a9ad2-146">tables. sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-146">tables.sql</span></span>

    -   <span data-ttu-id="a9ad2-147">函數 .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-147">functions.sql</span></span>

    -   <span data-ttu-id="a9ad2-148">views .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-148">views.sql</span></span>

    -   <span data-ttu-id="a9ad2-149">程式 sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-149">procedures.sql</span></span>

    -   <span data-ttu-id="a9ad2-150">trigger. sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-150">triggers.sql</span></span>

    -   <span data-ttu-id="a9ad2-151">資料 \ _codes .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-151">data\_codes.sql</span></span>

    -   <span data-ttu-id="a9ad2-152">資料 \ _messages .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-152">data\_messages.sql</span></span>

    -   <span data-ttu-id="a9ad2-153">資料 \ _defaults .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-153">data\_defaults.sql</span></span>

    -   <span data-ttu-id="a9ad2-154">[警示] \ _jobs</span><span class="sxs-lookup"><span data-stu-id="a9ad2-154">alerts\_jobs.sql</span></span>

    -   <span data-ttu-id="a9ad2-155">dbversion</span><span class="sxs-lookup"><span data-stu-id="a9ad2-155">dbversion.sql</span></span>

2.  <span data-ttu-id="a9ad2-156">視需要查看並修改檔案 `database.sql` 。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-156">Review and modify, if necessary, the `database.sql` file.</span></span> <span data-ttu-id="a9ad2-157">預設設定會將 [APPVIRTDB] 命名為 [資料庫]。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-157">The default settings will name the database “APPVIRTDB.”</span></span>

    -   <span data-ttu-id="a9ad2-158">如有必要， `APPVIRTDB` 請將使用的範例取代為 `database name` 。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-158">If necessary replace instances of `APPVIRTDB` with the `database name` that will be used.</span></span>

    -   <span data-ttu-id="a9ad2-159">`FILENAME`在腳本中修改要建立資料庫之 SQL Server 的適當路徑的屬性。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-159">Modify the `FILENAME` property in the script with the appropriate path for the SQL Server where the database will be created.</span></span>

3.  <span data-ttu-id="a9ad2-160">如有需要，請 `database name [APPVIRTDB]` 在資料庫 .sql 檔案中使用的檔案中查看和修改 `roles.sql` 。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-160">Review and modify, if necessary, the `database name [APPVIRTDB]` in the `roles.sql` file that was used in the database.sql file.</span></span>

****

### <span data-ttu-id="a9ad2-161">如何使用批次處理檔案自動化處理常式的範例</span><span class="sxs-lookup"><span data-stu-id="a9ad2-161">Example of how to automate the process using batch files</span></span>

<span data-ttu-id="a9ad2-162">如果使用的話，提供的兩個範例批次檔案會以下列方式執行 SQL 腳本：</span><span class="sxs-lookup"><span data-stu-id="a9ad2-162">If used, the two sample batch files provided run the SQL scripts in the following manner:</span></span>

1.  **<span data-ttu-id="a9ad2-163">Create\_schema.bat （1）</span><span class="sxs-lookup"><span data-stu-id="a9ad2-163">Create\_schema.bat (1)</span></span>**

    -   <span data-ttu-id="a9ad2-164">database .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-164">database.sql</span></span>

    -   <span data-ttu-id="a9ad2-165">roles. sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-165">roles.sql</span></span>

2.  **<span data-ttu-id="a9ad2-166">Create\_tables.bat （2）</span><span class="sxs-lookup"><span data-stu-id="a9ad2-166">Create\_tables.bat (2)</span></span>**

    -   <span data-ttu-id="a9ad2-167">表格 \ _CODES .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-167">table\_CODES.sql</span></span>

    -   <span data-ttu-id="a9ad2-168">函數 \ _before \ _tables .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-168">functions\_before\_tables.sql</span></span>

    -   <span data-ttu-id="a9ad2-169">tables. sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-169">tables.sql</span></span>

    -   <span data-ttu-id="a9ad2-170">函數 .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-170">functions.sql</span></span>

    -   <span data-ttu-id="a9ad2-171">views .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-171">views.sql</span></span>

    -   <span data-ttu-id="a9ad2-172">程式 sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-172">procedures.sql</span></span>

    -   <span data-ttu-id="a9ad2-173">trigger. sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-173">triggers.sql</span></span>

    -   <span data-ttu-id="a9ad2-174">資料 \ _codes .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-174">data\_codes.sql</span></span>

    -   <span data-ttu-id="a9ad2-175">資料 \ _messages .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-175">data\_messages.sql</span></span>

    -   <span data-ttu-id="a9ad2-176">資料 \ _defaults .sql</span><span class="sxs-lookup"><span data-stu-id="a9ad2-176">data\_defaults.sql</span></span>

    -   <span data-ttu-id="a9ad2-177">[警示] \ _jobs</span><span class="sxs-lookup"><span data-stu-id="a9ad2-177">alerts\_jobs.sql</span></span>

    -   <span data-ttu-id="a9ad2-178">dbversion</span><span class="sxs-lookup"><span data-stu-id="a9ad2-178">dbversion.sql</span></span>

**<span data-ttu-id="a9ad2-179">注意</span><span class="sxs-lookup"><span data-stu-id="a9ad2-179">Note</span></span>**  
<span data-ttu-id="a9ad2-180">請謹慎考慮修改腳本時必須採取的做法，且只能由具備適當知識的人來完成。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-180">Careful consideration when modifying the scripts must be taken and should only be done by someone with the appropriate knowledge.</span></span> <span data-ttu-id="a9ad2-181">此外，只提供下列範例檔案應該會變更： **create\_schema.bat**、 **create\_tables.bat**、 **.sql**以及**roles .sql**。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-181">Also, of the sample files presented only the following should be changed: **create\_schema.bat**, **create\_tables.bat**, **database.sql**, and **roles.sql**.</span></span> <span data-ttu-id="a9ad2-182">所有其他檔案不應以任何方式修改，因為這可能導致資料庫無法正確建立，這會導致安裝 App-v 服務失敗。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-182">All other files should not be modified in any way as this could cause the database to be created incorrectly, which will lead to the failure of App-V services to be installed.</span></span>



<span data-ttu-id="a9ad2-183">兩個範例批次檔案必須放在電腦上複製的其餘 SQL 腳本所在的同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-183">The two sample batch files must be placed in the same directory where the rest of the SQL scripts were copied to on the computer.</span></span>

1.  <span data-ttu-id="a9ad2-184">執行範例**create\_schema.bat**檔案以建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-184">Run the sample **create\_schema.bat** file to create the database.</span></span> <span data-ttu-id="a9ad2-185">此腳本需要幾秒鐘的時間才能完成，不應該中斷。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-185">This script will take several seconds to complete and should not be interrupted.</span></span>

    -   <span data-ttu-id="a9ad2-186">從複製檔案的目錄執行 [建立 schema.bat 檔案]。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-186">Run the create schema.bat file from the directory where it was copied to.</span></span> <span data-ttu-id="a9ad2-187">語法為： "Create\_schema.bat `SQLSERVERNAME` "</span><span class="sxs-lookup"><span data-stu-id="a9ad2-187">Syntax is: “Create\_schema.bat `SQLSERVERNAME`”</span></span>

        ![AppV46SQLcreatebat](images/appv46sqlcreatebat.bmp)

    -   <span data-ttu-id="a9ad2-189">如果此腳本在建立新的「APPVIRTDB」資料庫時失敗，請視指示查看記錄來修正問題。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-189">If this script fails during the creation of the new “APPVIRTDB” database, check the log as indicated to correct the issue.</span></span> <span data-ttu-id="a9ad2-190">您必須刪除由部分執行腳本所建立的資料庫，以確保後續的嘗試將能正常運作。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-190">It will be necessary to delete the database that was created with a partial running of the scripts in order to ensure that subsequent attempts will work properly.</span></span>

2.  <span data-ttu-id="a9ad2-191">執行檔案 `create_tables.bat` 以建立資料庫中的資料表。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-191">Run the `create_tables.bat` file to create the tables in the database.</span></span> <span data-ttu-id="a9ad2-192">此腳本需要幾秒鐘的時間才能完成，不應該中斷。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-192">This script will take several seconds to complete and should not be interrupted.</span></span>

    -   <span data-ttu-id="a9ad2-193">從複製檔案的目錄執行 create\_tables.bat 檔案。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-193">Run the create\_tables.bat file from the directory where it was copied.</span></span> <span data-ttu-id="a9ad2-194">語法為： "create\_tables.bat `SQLSERVERNAME DBNAME` "</span><span class="sxs-lookup"><span data-stu-id="a9ad2-194">Syntax is: “create\_tables.bat `SQLSERVERNAME DBNAME`”</span></span>

        ![app-v 4.6 sql create\-table.bat](images/appv46sqlcreate-tablebat.gif)

        <span data-ttu-id="a9ad2-196">如果在建立資料表期間腳本失敗，請視指示查看記錄來修正問題。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-196">If the script fails during the creation of the tables, check the log as indicated to correct the issue.</span></span> <span data-ttu-id="a9ad2-197">您必須先刪除資料庫並執行 create\_schema.bat，才能嘗試在所有後續嘗試上執行 create\_tables.bat 檔案。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-197">It will be necessary to delete the database and run create\_schema.bat before attempting to run the create\_tables.bat file on all subsequent attempts.</span></span>

### <span data-ttu-id="a9ad2-198">在 App-v 資料庫上設定許可權</span><span class="sxs-lookup"><span data-stu-id="a9ad2-198">Setting permissions on the App-V database</span></span>

<span data-ttu-id="a9ad2-199">您必須在 SQL server 上建立下列帳戶，並將特定許可權和角色新增至新資料庫，以進行 App V 環境的安裝、部署及持續管理。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-199">The following accounts will need to be created on the SQL server with specific permissions and roles to the new database for the installation, deployment and ongoing administration of the App-V environment.</span></span>

-   <span data-ttu-id="a9ad2-200">在 SQL Server 上建立 app-v 系統管理員群組的登入，並將 [domain\\App-V 系統管理員] 的 APPVIRTDB 資料庫（其中，"domain" 和 "App-v administrator"）新增至 [SFTAdmin] 和 SFTEveryone 資料庫角色。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-200">Create a login for the App-V administrators group on the SQL Server and the APPVIRTDB database for the “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment) and add them to the SFTAdmin and SFTEveryone database role.</span></span>

    ![app-v 4.6 sql 腳本設定許可權和角色](images/appv46sqlscriptsetpermsroles.gif)

-   <span data-ttu-id="a9ad2-202">在全域層級授與此群組「查看任何定義」許可權（這可讓 Microsoft Application Virtualization 管理伺服器設定處理常式驗證管理伺服器登入已存在）。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-202">Grant this group “VIEW ANY DEFINITION” permission at the global level (This allows the Microsoft Application Virtualization Management Server setup process to verify that the Management Server login already exists).</span></span> <span data-ttu-id="a9ad2-203">在 MS-SQL 2005 和更新版本中，已新增對 master 中所含中繼資料的存取限制。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-203">Under MS-SQL 2005 and above access restrictions to the metadata contained in master.db were added.</span></span> <span data-ttu-id="a9ad2-204">在上一個步驟中建立的使用者，預設不會擁有伺服器安裝所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-204">The user created in the previous step will by default not have the rights needed by the server installation.</span></span> <span data-ttu-id="a9ad2-205">開啟先前建立的 [登入屬性] 的屬性- &gt; Securables。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-205">Open the properties of the previously created login, Login Properties-&gt;Securables.</span></span> <span data-ttu-id="a9ad2-206">針對 [查看任何定義]，新增資料庫實例並啟用「授與」，如下列螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-206">Add the Database instance and enable “GRANT” for “View any definition” as shown in the screenshot below.</span></span>

    ![app-v 4.6 sql 腳本授與 perm 以查看任何定義](images/appv46sqlscriptviewanydef.gif)

-   <span data-ttu-id="a9ad2-208">在上一個步驟中建立的登入角色 \ _ASSIGNMENTS 表格中，將角色新增到 [允許 App-v 管理員存取應用程式虛擬化管理主控台]，角色 = "管理員" 和群組 \ _ref = "domain\\App-V 系統管理員" （其中，"domain" 和 "App-v 系統管理員" 將會變更，以反映您自己的環境）。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-208">Add a role to the ROLE\_ASSIGNMENTS table for the login created in the previous step to allow App-V administrators access to the Application Virtualization Management Console, with role = “ADMIN” and group\_ref = “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment).</span></span>

    ![app-v 4.6 sql 腳本角色指派](images/appv46sqlscriptroleassign.gif)

-   <span data-ttu-id="a9ad2-210">針對管理伺服器建立 SQL Server 和 App-v 資料庫的登入。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-210">Create login for SQL Server and App-V database for the Management Server.</span></span> <span data-ttu-id="a9ad2-211">這個帳戶是由 Microsoft 應用程式虛擬化管理伺服器用來連線到資料存放區，且負責為流程式應用程式服務用戶端要求。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-211">This account is used by the Microsoft Application Virtualization Management Server to connect to the data store and is responsible for servicing client requests for streamed applications.</span></span> <span data-ttu-id="a9ad2-212">根據 SQL Server 和管理伺服器的安裝位置，有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="a9ad2-212">There are two options, depending on where the SQL Server and Management Server are to be installed:</span></span>

    1.  <span data-ttu-id="a9ad2-213">如果管理伺服器與 SQL Server 將要安裝在同一部電腦上，請為 NT AUTHORITY\\NETWORK SERVICE 新增登入，並將其新增至 SFTUser 和 SFTEveryone 資料庫角色。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-213">If Management Server and SQL Server are going to be installed on the same computer, add a login for NT AUTHORITY\\NETWORK SERVICE and add it to the SFTUser and SFTEveryone database roles.</span></span>

    2.  <span data-ttu-id="a9ad2-214">如果要在不同的電腦上安裝管理伺服器與 SQL Server，請在 [domain\\App-V Server Name $] （其中，"App-v Server Name" 是安裝 App-v 管理伺服器的伺服器名稱）上新增 [登入]，然後將它新增到 SFTUser 和 SFTEveryone 資料庫角色。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-214">If the Management Server and SQL Server are to be installed on different computers, add a login for “domain\\App-V Server Name$” (where “App-V Server Name” is the name of the server where the App-V Management Server will be installed) and add it to the SFTUser and SFTEveryone database roles.</span></span>

-   <span data-ttu-id="a9ad2-215">開啟 SQL 視窗中的 [查詢] 視窗，然後執行下列 SQL：</span><span class="sxs-lookup"><span data-stu-id="a9ad2-215">Open the query window on the SQL window and run the following SQL:</span></span>

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    <span data-ttu-id="a9ad2-216">在上一個步驟中，APPVIRTDB 是在 SQL Server 上建立的應用程式 V 資料庫的名稱，而要執行 App-v 伺服器安裝的使用者必須是「domain\\App-V 系統管理員」的成員（其中，"domain" 和 "App-v 系統管理員" 將會變更，以反映您自己的環境）。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-216">Where the APPVIRTDB is the name of the App-V Database created on the SQL Server in the previous step, and the user who is going to do the install of the App-v server needs to be a member of “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment).</span></span>

### <span data-ttu-id="a9ad2-217">結構管理員要執行的工作</span><span class="sxs-lookup"><span data-stu-id="a9ad2-217">Tasks to be performed by the Infrastructure administrators</span></span>

1.  <span data-ttu-id="a9ad2-218">[App-v 管理員] 群組中的系統管理員應該安裝 App-v。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-218">Administrator in the “App-V Admins” group should install App-V.</span></span>

    <span data-ttu-id="a9ad2-219">使用 SQL 系統管理員的資訊來選取在上述步驟中建立的 SQL Server 和資料庫。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-219">Use information from the SQL administrators for selecting the SQL Server and database created in the previous steps.</span></span>

2.  <span data-ttu-id="a9ad2-220">[App-v Admins] 群組中的系統管理員會登入應用程式虛擬化管理主控台，然後從管理主控台刪除下列物件。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-220">Administrator in the “App-V Admins” group logs in to Application Virtualization Management Console and deletes the following objects from the Management Console.</span></span>

    **<span data-ttu-id="a9ad2-221">警告</span><span class="sxs-lookup"><span data-stu-id="a9ad2-221">Warning</span></span>**  
    <span data-ttu-id="a9ad2-222">這是必要的，因為傳統的安裝程式會在您針對現有的資料庫執行安裝時，填入資料庫中未填入的特定記錄。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-222">This is required as the traditional setup populates certain records in the database that are not populated if you run the install against an already existing database.</span></span> <span data-ttu-id="a9ad2-223">刪除下列物件：</span><span class="sxs-lookup"><span data-stu-id="a9ad2-223">Delete the following objects:</span></span>

    -   <span data-ttu-id="a9ad2-224">在 [伺服器群組] 下，"預設伺服器群組，" 刪除 [Application Virtualization 管理伺服器]</span><span class="sxs-lookup"><span data-stu-id="a9ad2-224">Under “Server Groups,” “Default Server Group,” delete “Application Virtualization Management Server”</span></span>

    -   <span data-ttu-id="a9ad2-225">在 [伺服器群組] 下，刪除 [預設伺服器群組]</span><span class="sxs-lookup"><span data-stu-id="a9ad2-225">Under “Server Groups,” delete “Default Server Group”</span></span>

    -   <span data-ttu-id="a9ad2-226">[提供者原則] 底下的 [刪除「預設提供者」</span><span class="sxs-lookup"><span data-stu-id="a9ad2-226">Under “Provider Policies,” delete “Default Provider”</span></span>



3.  <span data-ttu-id="a9ad2-227">然後，應用程式 V 管理員群組中的系統管理員會建立：</span><span class="sxs-lookup"><span data-stu-id="a9ad2-227">Administrator in the App-V admins group should then create:</span></span>

    -   <span data-ttu-id="a9ad2-228">在 [提供者原則] 底下，建立新的提供者原則</span><span class="sxs-lookup"><span data-stu-id="a9ad2-228">Under “Provider Policies,” create a New Provider Policy</span></span>

    -   <span data-ttu-id="a9ad2-229">建立「預設伺服器群組」</span><span class="sxs-lookup"><span data-stu-id="a9ad2-229">Create a “Default Server Group”</span></span>

        **<span data-ttu-id="a9ad2-230">注意</span><span class="sxs-lookup"><span data-stu-id="a9ad2-230">Note</span></span>**  
        <span data-ttu-id="a9ad2-231">您必須建立 [預設伺服器] 群組，即使您將不會使用。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-231">You must create a “Default Server” group even if you will not be used.</span></span> <span data-ttu-id="a9ad2-232">伺服器安裝程式在嘗試新增伺服器時，只會尋找「預設伺服器群組」。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-232">The server installer only looks for the "Default Server Group" when trying to add the server.</span></span>  <span data-ttu-id="a9ad2-233">如果沒有「預設伺服器群組」，則安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-233">If there is no "Default Server Group" then the installation will fail.</span></span> <span data-ttu-id="a9ad2-234">如果您打算使用不正確的預設伺服器群組，只要將後續的 App-v 管理伺服器新增到您的基礎結構，就必須保留「預設伺服器群組」。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-234">If you plan on using server groups other than the default that is fine, it’s just necessary to retain the "Default Server Group" if you plan on adding subsequent App-V Management Servers to your infrastructure.</span></span>



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## <span data-ttu-id="a9ad2-235">總結</span><span class="sxs-lookup"><span data-stu-id="a9ad2-235">Conclusion</span></span>


<span data-ttu-id="a9ad2-236">總之，本檔中的資訊可讓管理員與 SQL 系統管理員共同作業，以開發適用于組織中安全性與管理部門的部署路徑。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-236">In conclusion, the information in this document allows an administrator to work with the SQL administrators to develop a deployment path that works for the security and administrative divisions in an organization.</span></span> <span data-ttu-id="a9ad2-237">閱讀此檔並測試已記錄的工作之後，系統管理員應該準備好在此類型的環境中實現其 App-v 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="a9ad2-237">After reading this document and testing the tasks documented, an administrator should be ready to implement their App-V infrastructure in this type of environment.</span></span>









