---
title: 如何部署 App-V 5.0 Server
description: 如何部署 App-V 5.0 Server
author: dansimp
ms.assetid: 4f8f16af-7d74-42b4-84b8-b04ce668225d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b94bab16349751aacf0aca0f8c2e5ac5a6ae6da7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800528"
---
# <span data-ttu-id="9c357-103">如何部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="9c357-103">How to Deploy the App-V 5.0 Server</span></span>


<span data-ttu-id="9c357-104">使用下列程式來安裝 App-v 5.0 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9c357-104">Use the following procedure to install the App-V 5.0 server.</span></span> <span data-ttu-id="9c357-105">如需有關部署 App-v 5.0 SP3 伺服器的資訊，請參閱[關於 app-v 5.0 sp3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)。</span><span class="sxs-lookup"><span data-stu-id="9c357-105">For information about deploying the App-V 5.0 SP3 Server, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3).</span></span>

**<span data-ttu-id="9c357-106">開始之前：</span><span class="sxs-lookup"><span data-stu-id="9c357-106">Before you start:</span></span>**

-   <span data-ttu-id="9c357-107">確定您已安裝必備軟體。</span><span class="sxs-lookup"><span data-stu-id="9c357-107">Ensure that you’ve installed prerequisite software.</span></span> <span data-ttu-id="9c357-108">請參閱[App-V 5.0 先決條件](app-v-50-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="9c357-108">See [App-V 5.0 Prerequisites](app-v-50-prerequisites.md).</span></span>

-   <span data-ttu-id="9c357-109">請參閱[應用程式 V 5.0 安全性考慮](app-v-50-security-considerations.md)的伺服器區段。</span><span class="sxs-lookup"><span data-stu-id="9c357-109">Review the server section of [App-V 5.0 Security Considerations](app-v-50-security-considerations.md).</span></span>

-   <span data-ttu-id="9c357-110">指定將託管每個元件的埠。</span><span class="sxs-lookup"><span data-stu-id="9c357-110">Specify a port where each component will be hosted.</span></span>

-   <span data-ttu-id="9c357-111">新增防火牆規則，以允許傳入要求存取指定的埠。</span><span class="sxs-lookup"><span data-stu-id="9c357-111">Add firewall rules to allow incoming requests to access the specified ports.</span></span>

-   <span data-ttu-id="9c357-112">如果您使用 SQL 腳本（而不是 Windows 安裝程式）來設定管理資料庫或報表資料庫，您必須先執行 SQL 腳本，然後才能安裝管理伺服器或報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="9c357-112">If you use SQL scripts, instead of the Windows Installer, to set up the Management database or Reporting database, you must run the SQL scripts before installing the Management Server or Reporting Server.</span></span> <span data-ttu-id="9c357-113">瞭解[如何使用 SQL 腳本部署 App-v 資料庫](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)。</span><span class="sxs-lookup"><span data-stu-id="9c357-113">See [How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md).</span></span>

**<span data-ttu-id="9c357-114">若要安裝應用程式-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="9c357-114">To install the App-V 5.0 server</span></span>**

1. <span data-ttu-id="9c357-115">將 App-v 5.0 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="9c357-115">Copy the App-V 5.0 server installation files to the computer on which you want to install it.</span></span>

2. <span data-ttu-id="9c357-116">以管理員身分按一下並執行**appv\_server\_setup.exe** ，然後按一下 [**安裝**]，啟動 App V 5.0 伺服器的安裝。</span><span class="sxs-lookup"><span data-stu-id="9c357-116">Start the App-V 5.0 server installation by right-clicking and running **appv\_server\_setup.exe** as an administrator, and then click **Install**.</span></span>

3. <span data-ttu-id="9c357-117">查看並接受授權條款，並選擇是否要啟用 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="9c357-117">Review and accept the license terms, and choose whether to enable Microsoft updates.</span></span>

4. <span data-ttu-id="9c357-118">在 [**功能選取**] 頁面上，選取 [下列所有元件]。</span><span class="sxs-lookup"><span data-stu-id="9c357-118">On the **Feature Selection** page, select all of the following components.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="9c357-119">元件</span><span class="sxs-lookup"><span data-stu-id="9c357-119">Component</span></span></th>
   <th align="left"><span data-ttu-id="9c357-120">說明</span><span class="sxs-lookup"><span data-stu-id="9c357-120">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9c357-121">管理伺服器</span><span class="sxs-lookup"><span data-stu-id="9c357-121">Management server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-122">提供 App-v 基礎結構的整體管理功能。</span><span class="sxs-lookup"><span data-stu-id="9c357-122">Provides overall management functionality for the App-V infrastructure.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="9c357-123">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="9c357-123">Management database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-124">協助 App-v 管理的資料庫 predeployments。</span><span class="sxs-lookup"><span data-stu-id="9c357-124">Facilitates database predeployments for App-V management.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9c357-125">發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="9c357-125">Publishing server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-126">提供虛擬應用程式的託管與流式處理功能。</span><span class="sxs-lookup"><span data-stu-id="9c357-126">Provides hosting and streaming functionality for virtual applications.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="9c357-127">報表伺服器</span><span class="sxs-lookup"><span data-stu-id="9c357-127">Reporting server</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-128">提供 App-v 5.0 reporting services。</span><span class="sxs-lookup"><span data-stu-id="9c357-128">Provides App-V 5.0 reporting services.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9c357-129">報表資料庫</span><span class="sxs-lookup"><span data-stu-id="9c357-129">Reporting database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-130">協助 App-v 報告的資料庫 predeployments。</span><span class="sxs-lookup"><span data-stu-id="9c357-130">Facilitates database predeployments for App-V reporting.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

5. <span data-ttu-id="9c357-131">在 [**安裝位置**] 頁面上，接受要安裝所選元件的預設位置，或在 [**安裝位置**] 行上輸入新路徑來變更位置。</span><span class="sxs-lookup"><span data-stu-id="9c357-131">On the **Installation Location** page, accept the default location where the selected components will be installed, or change the location by typing a new path on the **Installation Location** line.</span></span>

6. <span data-ttu-id="9c357-132">在初始 [**建立新的管理資料庫**] 頁面上，選取下列適當的選項，以設定**Microsoft SQL Server 實例**與**管理伺服器資料庫**。</span><span class="sxs-lookup"><span data-stu-id="9c357-132">On the initial **Create New Management Database** page, configure the **Microsoft SQL Server instance** and **Management Server database** by selecting the appropriate option below.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="9c357-133">方法</span><span class="sxs-lookup"><span data-stu-id="9c357-133">Method</span></span></th>
   <th align="left"><span data-ttu-id="9c357-134">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="9c357-134">What you need to do</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9c357-135">您使用的是自訂的 Microsoft SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="9c357-135">You are using a custom Microsoft SQL Server instance.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-136">選取 <strong> [使用自訂實例] </strong> ，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-136">Select <strong>Use the custom instance</strong>, and type the name of the instance.</span></span></p>
   <p><span data-ttu-id="9c357-137">使用格式 <strong> INSTANCENAME </strong> 。</span><span class="sxs-lookup"><span data-stu-id="9c357-137">Use the format <strong>INSTANCENAME</strong>.</span></span> <span data-ttu-id="9c357-138">假設的安裝位置是本機電腦。</span><span class="sxs-lookup"><span data-stu-id="9c357-138">The assumed installation location is the local computer.</span></span></p>
   <p><span data-ttu-id="9c357-139">不支援：使用格式 <strong> ServerName </strong> &lt; 強 &gt; 實例的伺服器名稱 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="9c357-139">Not supported: A server name using the format <strong>ServerName</strong>&lt;strong&gt;INSTANCE</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="9c357-140">您使用的是自訂資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-140">You are using a custom database name.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-141">選取 <strong> [自訂設定] </strong> ，然後輸入資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-141">Select <strong>Custom configuration</strong> and type the database name.</span></span></p>
   <p><span data-ttu-id="9c357-142">資料庫名稱必須是唯一的，否則安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9c357-142">The database name must be unique, or the installation will fail.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="9c357-143">在 [**設定**] 頁面上，接受 [**使用此本機電腦**的預設值]。</span><span class="sxs-lookup"><span data-stu-id="9c357-143">On the **Configure** page, accept the default value **Use this local computer**.</span></span>

   **<span data-ttu-id="9c357-144">注意</span><span class="sxs-lookup"><span data-stu-id="9c357-144">Note</span></span>**  
   <span data-ttu-id="9c357-145">如果您要並排安裝管理伺服器與管理資料庫，此頁面上的某些選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="9c357-145">If you are installing the Management server and Management database side by side, some options on this page are not available.</span></span> <span data-ttu-id="9c357-146">在這種情況下，預設會選取適當的選項，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="9c357-146">In this case, the appropriate options are selected by default and cannot be changed.</span></span>

     

8. <span data-ttu-id="9c357-147">在初始 [**建立新的報表資料庫**] 頁面上，選取以下適當的選項，以設定**Microsoft SQL Server 實例**與**報表伺服器資料庫**。</span><span class="sxs-lookup"><span data-stu-id="9c357-147">On the initial **Create New Reporting Database** page, configure the **Microsoft SQL Server instance** and **Reporting Server database** by selecting the appropriate option below.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="9c357-148">方法</span><span class="sxs-lookup"><span data-stu-id="9c357-148">Method</span></span></th>
   <th align="left"><span data-ttu-id="9c357-149">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="9c357-149">What you need to do</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9c357-150">您使用的是自訂的 Microsoft SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="9c357-150">You are using a custom Microsoft SQL Server instance.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-151">選取 <strong> [使用自訂實例] </strong> ，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-151">Select <strong>Use the custom instance</strong>, and type the name of the instance.</span></span></p>
   <p><span data-ttu-id="9c357-152">使用格式 <strong> INSTANCENAME </strong> 。</span><span class="sxs-lookup"><span data-stu-id="9c357-152">Use the format <strong>INSTANCENAME</strong>.</span></span> <span data-ttu-id="9c357-153">假設的安裝位置是本機電腦。</span><span class="sxs-lookup"><span data-stu-id="9c357-153">The assumed installation location is the local computer.</span></span></p>
   <p><span data-ttu-id="9c357-154">不支援：使用格式 <strong> ServerName </strong> &lt; 強 &gt; 實例的伺服器名稱 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="9c357-154">Not supported: A server name using the format <strong>ServerName</strong>&lt;strong&gt;INSTANCE</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="9c357-155">您使用的是自訂資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-155">You are using a custom database name.</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9c357-156">選取 <strong> [自訂設定] </strong> ，然後輸入資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-156">Select <strong>Custom configuration</strong> and type the database name.</span></span></p>
   <p><span data-ttu-id="9c357-157">資料庫名稱必須是唯一的，否則安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9c357-157">The database name must be unique, or the installation will fail.</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

9. <span data-ttu-id="9c357-158">在 [**設定**] 頁面上，接受預設值： [**使用此本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="9c357-158">On the **Configure** page, accept the default value: **Use this local computer**.</span></span>

   **<span data-ttu-id="9c357-159">注意</span><span class="sxs-lookup"><span data-stu-id="9c357-159">Note</span></span>**  
   <span data-ttu-id="9c357-160">如果您要並排安裝管理伺服器與管理資料庫，此頁面上的某些選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="9c357-160">If you are installing the Management server and Management database side by side, some options on this page are not available.</span></span> <span data-ttu-id="9c357-161">在這種情況下，預設會選取適當的選項，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="9c357-161">In this case, the appropriate options are selected by default and cannot be changed.</span></span>

     

10. <span data-ttu-id="9c357-162">在 [**設定**（管理伺服器配置）] 頁面上，指定以下專案：</span><span class="sxs-lookup"><span data-stu-id="9c357-162">On the **Configure** (Management Server Configuration) page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="9c357-163">要設定的專案</span><span class="sxs-lookup"><span data-stu-id="9c357-163">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="9c357-164">描述與範例</span><span class="sxs-lookup"><span data-stu-id="9c357-164">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="9c357-165">輸入擁有足夠許可權的 AD 群組，以管理 App-v 環境。</span><span class="sxs-lookup"><span data-stu-id="9c357-165">Type the AD group with sufficient permissions to manage the App-V environment.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-166">範例： MyDomain\MyUser</span><span class="sxs-lookup"><span data-stu-id="9c357-166">Example: MyDomain\MyUser</span></span></p>
    <p><span data-ttu-id="9c357-167">安裝之後，您可以使用管理主控台新增其他使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="9c357-167">After installation, you can add additional users or groups by using the Management console.</span></span> <span data-ttu-id="9c357-168">不過，不支援全域安全性群組和 Active Directory 網域服務（AD DS）通訊群組。</span><span class="sxs-lookup"><span data-stu-id="9c357-168">However, global security groups and Active Directory Domain Services (AD DS) distribution groups are not supported.</span></span> <span data-ttu-id="9c357-169">您必須使用「 <strong> 網域本機」 </strong> 或「通用」 <strong> </strong> 群組才能執行此動作。</span><span class="sxs-lookup"><span data-stu-id="9c357-169">You must use <strong>Domain local</strong> or <strong>Universal</strong> groups are required to perform this action.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="9c357-170">網站名稱 </strong> ：指定將用來執行發佈服務的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-170">Website name</strong>: Specify the custom name that will be used to run the publishing service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-171">如果您沒有自訂名稱，請不要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="9c357-171">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="9c357-172">埠系結 </strong> ：指定將由 app-v 使用的唯一端口號碼。</span><span class="sxs-lookup"><span data-stu-id="9c357-172">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-173">範例： <strong> 12345</span><span class="sxs-lookup"><span data-stu-id="9c357-173">Example: <strong>12345</span></span></strong></p>
    <p><span data-ttu-id="9c357-174">確定指定的埠未由其他網站使用。</span><span class="sxs-lookup"><span data-stu-id="9c357-174">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

11. <span data-ttu-id="9c357-175">在 [**設定\*\*\*\*發佈伺服器**設定] 頁面上，指定以下專案：</span><span class="sxs-lookup"><span data-stu-id="9c357-175">On the **Configure** **Publishing Server Configuration** page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="9c357-176">要設定的專案</span><span class="sxs-lookup"><span data-stu-id="9c357-176">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="9c357-177">描述與範例</span><span class="sxs-lookup"><span data-stu-id="9c357-177">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="9c357-178">指定管理服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="9c357-178">Specify the URL for the management service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-179">範例<a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</span><span class="sxs-lookup"><span data-stu-id="9c357-179">Example: <a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</span></span></a></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="9c357-180">網站名稱 </strong> ：指定將用來執行發佈服務的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-180">Website name</strong>: Specify the custom name that will be used to run the publishing service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-181">如果您沒有自訂名稱，請不要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="9c357-181">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="9c357-182">埠系結 </strong> ：指定將由 app-v 使用的唯一端口號碼。</span><span class="sxs-lookup"><span data-stu-id="9c357-182">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-183">範例：54321</span><span class="sxs-lookup"><span data-stu-id="9c357-183">Example: 54321</span></span></p>
    <p><span data-ttu-id="9c357-184">確定指定的埠未由其他網站使用。</span><span class="sxs-lookup"><span data-stu-id="9c357-184">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

12. <span data-ttu-id="9c357-185">在 [**報表伺服器**] 頁面上，指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="9c357-185">On the **Reporting Server** page, specify the following:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="9c357-186">要設定的專案</span><span class="sxs-lookup"><span data-stu-id="9c357-186">Item to configure</span></span></th>
    <th align="left"><span data-ttu-id="9c357-187">描述與範例</span><span class="sxs-lookup"><span data-stu-id="9c357-187">Description and examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="9c357-188">網站名稱 </strong> ：指定將用來執行報表服務的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="9c357-188">Website name</strong>: Specify the custom name that will be used to run the Reporting Service.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-189">如果您沒有自訂名稱，請不要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="9c357-189">If you do not have a custom name, do not make any changes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="9c357-190">埠系結 </strong> ：指定將由 app-v 使用的唯一端口號碼。</span><span class="sxs-lookup"><span data-stu-id="9c357-190">Port binding</strong>: Specify a unique port number that will be used by App-V.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="9c357-191">範例：55555</span><span class="sxs-lookup"><span data-stu-id="9c357-191">Example: 55555</span></span></p>
    <p><span data-ttu-id="9c357-192">確定指定的埠未由其他網站使用。</span><span class="sxs-lookup"><span data-stu-id="9c357-192">Ensure that the port specified is not being used by another website.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

13. <span data-ttu-id="9c357-193">若要開始安裝，請在 [**就緒**] 頁面上按一下 [**安裝**]，然後按一下 [**完成**] 頁面上的 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="9c357-193">To start the installation, click **Install** on the **Ready** page, and then click **Close** on the **Finished** page.</span></span>

14. <span data-ttu-id="9c357-194">若要確認安裝程式已順利完成，請開啟網頁瀏覽器，然後輸入下列 URL：</span><span class="sxs-lookup"><span data-stu-id="9c357-194">To verify that the setup completed successfully, open a web browser, and type the following URL:</span></span>

    <span data-ttu-id="9c357-195">**HTTP:// &lt;管理伺服器電腦名稱稱 &gt; ： &lt; 管理服務埠編號 &gt; /Console.html**。</span><span class="sxs-lookup"><span data-stu-id="9c357-195">**http://&lt;Management server machine name&gt;:&lt;Management service port number&gt;/Console.html**.</span></span>

    <span data-ttu-id="9c357-196">範例： **http://localhost:12345/console.html** 。</span><span class="sxs-lookup"><span data-stu-id="9c357-196">Example: **http://localhost:12345/console.html**.</span></span> <span data-ttu-id="9c357-197">如果安裝成功，則會顯示 App-v 管理主控台，沒有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="9c357-197">If the installation succeeded, the App-V Management console is displayed with no errors.</span></span>

    <span data-ttu-id="9c357-198">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="9c357-198">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="9c357-199">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="9c357-199">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="9c357-200">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="9c357-200">Got an App-V issue?</span></span>** <span data-ttu-id="9c357-201">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="9c357-201">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="9c357-202">相關主題</span><span class="sxs-lookup"><span data-stu-id="9c357-202">Related topics</span></span>


[<span data-ttu-id="9c357-203">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="9c357-203">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="9c357-204">如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫</span><span class="sxs-lookup"><span data-stu-id="9c357-204">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)

[<span data-ttu-id="9c357-205">如何在遠端電腦上安裝發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="9c357-205">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer.md)

[<span data-ttu-id="9c357-206">如何使用指令碼來部署 App-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="9c357-206">How to Deploy the App-V 5.0 Server Using a Script</span></span>](how-to-deploy-the-app-v-50-server-using-a-script.md)

[<span data-ttu-id="9c357-207">如何使用 PowerShell 在 App-V 5.0 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="9c357-207">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)

 

 





