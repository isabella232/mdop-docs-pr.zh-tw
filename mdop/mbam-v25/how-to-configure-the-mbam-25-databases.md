---
title: 如何設定 MBAM 2.5 資料庫
description: 如何設定 MBAM 2.5 資料庫
author: dansimp
ms.assetid: 66e1c81b-f785-4398-9175-bb5f112c2a35
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c11cb58d8fd9266bd0322e4cf9aa96256b7fbb6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811865"
---
# <span data-ttu-id="e98ab-103">如何設定 MBAM 2.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="e98ab-103">How to Configure the MBAM 2.5 Databases</span></span>


<span data-ttu-id="e98ab-104">本主題說明如何使用以下內容來設定 Microsoft BitLocker 管理和監控（MBAM）2.5 合規性與審核資料庫及復原資料庫</span><span class="sxs-lookup"><span data-stu-id="e98ab-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Compliance and Audit Database and the Recovery Database by using:</span></span>

-   <span data-ttu-id="e98ab-105">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e98ab-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="e98ab-106">[MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="e98ab-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="e98ab-107">指示是以[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)中的建議架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="e98ab-107">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="e98ab-108">開始設定前：</span><span class="sxs-lookup"><span data-stu-id="e98ab-108">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e98ab-109">步驟</span><span class="sxs-lookup"><span data-stu-id="e98ab-109">Step</span></span></th>
<th align="left"><span data-ttu-id="e98ab-110">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="e98ab-110">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e98ab-111">針對 MBAM 查看建議的架構。</span><span class="sxs-lookup"><span data-stu-id="e98ab-111">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="e98ab-112">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="e98ab-112">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e98ab-113">查看 MBAM 支援的設定。</span><span class="sxs-lookup"><span data-stu-id="e98ab-113">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="e98ab-114">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="e98ab-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e98ab-115">在每個伺服器上完成必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="e98ab-115">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="e98ab-116">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="e98ab-116">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="e98ab-117">僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 必備元件 </a> （如果適用）</span><span class="sxs-lookup"><span data-stu-id="e98ab-117">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e98ab-118">在您規劃設定 MBAM 伺服器功能的每個伺服器上，安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="e98ab-118">Install the MBAM Server software on each server where you plan to configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e98ab-119">注意</span><span class="sxs-lookup"><span data-stu-id="e98ab-119">Note</span></span></strong><br/><p><span data-ttu-id="e98ab-120">您可以使用 Windows PowerShell 或匯出的資料層應用程式（DAC）套件，將資料庫安裝至遠端 SQL Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="e98ab-120">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="e98ab-121">如需有關 DAC 套件的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 資料層應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e98ab-121">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="e98ab-122">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="e98ab-122">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e98ab-123">如果您打算使用 Windows powershell Cmdlet 來設定 MBAM 伺服器功能，請參閱使用 Windows PowerShell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="e98ab-123">Review the prerequisites for using Windows PowerShell if you plan to use Windows PowerShell cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="e98ab-124">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="e98ab-124">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e98ab-125">使用 Windows PowerShell 來設定資料庫</span><span class="sxs-lookup"><span data-stu-id="e98ab-125">To configure the databases by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="e98ab-126">開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="e98ab-126">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="e98ab-127">使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 來設定資料庫。</span><span class="sxs-lookup"><span data-stu-id="e98ab-127">Use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the databases.</span></span> <span data-ttu-id="e98ab-128">若要取得有關這個 Windows PowerShell Cmdlet 的資訊，請輸入**Get-help Enable-MbamDatabase**。</span><span class="sxs-lookup"><span data-stu-id="e98ab-128">To get information about this Windows PowerShell cmdlet, type **Get-Help Enable-MbamDatabase**.</span></span>

**<span data-ttu-id="e98ab-129">使用嚮導來設定合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="e98ab-129">To configure the Compliance and Audit Database by using the wizard</span></span>**

1. <span data-ttu-id="e98ab-130">在您想要設定資料庫的伺服器上，啟動 [ **MBAM 伺服器**設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="e98ab-130">On the server where you want to configure the databases, start the **MBAM Server Configuration** wizard.</span></span> <span data-ttu-id="e98ab-131">您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。</span><span class="sxs-lookup"><span data-stu-id="e98ab-131">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="e98ab-132">按一下 [**新增功能**]、選取 [**合規性] 和 [審核資料庫\*\*\*\*及復原資料庫**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e98ab-132">Click **Add New Features**, select **Compliance and Audit Database** and **Recovery Database**, and then click **Next**.</span></span> <span data-ttu-id="e98ab-133">嚮導會檢查資料庫的所有先決條件是否都已滿足。</span><span class="sxs-lookup"><span data-stu-id="e98ab-133">The wizard checks that all prerequisites for the databases have been met.</span></span>

3. <span data-ttu-id="e98ab-134">如果先決條件檢查成功，請按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="e98ab-134">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="e98ab-135">否則，請解決任何缺少的先決條件，然後**再次按一下 [檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="e98ab-135">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4. <span data-ttu-id="e98ab-136">使用下列說明，在嚮導中輸入欄位值：</span><span class="sxs-lookup"><span data-stu-id="e98ab-136">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e98ab-137">欄位</span><span class="sxs-lookup"><span data-stu-id="e98ab-137">Field</span></span></th>
   <th align="left"><span data-ttu-id="e98ab-138">描述</span><span class="sxs-lookup"><span data-stu-id="e98ab-138">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e98ab-139">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="e98ab-139">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-140">您正在設定合規性和審核資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-140">Name of the server where you are configuring the Compliance and Audit Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e98ab-141">注意</span><span class="sxs-lookup"><span data-stu-id="e98ab-141">Note</span></span></strong><br/><p><span data-ttu-id="e98ab-142">您必須在合規性和審核資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。</span><span class="sxs-lookup"><span data-stu-id="e98ab-142">You must add an exception on the Compliance and Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="e98ab-143">預設埠號碼是1433。</span><span class="sxs-lookup"><span data-stu-id="e98ab-143">The default port number is 1433.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e98ab-144">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="e98ab-144">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-145">儲存合規性和審核資料之資料庫實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-145">Name of the database instance where the compliance and audit data will be stored.</span></span> <span data-ttu-id="e98ab-146">您也必須指定資料庫資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="e98ab-146">You must also specify where the database information will be located.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e98ab-147">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="e98ab-147">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-148">儲存合規性資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-148">Name of the database that will store the compliance data.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e98ab-149">注意</span><span class="sxs-lookup"><span data-stu-id="e98ab-149">Note</span></span></strong><br/><p><span data-ttu-id="e98ab-150">如果您是從舊版 MBAM 升級，您必須使用與先前部署中所使用的名稱相同的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-150">If you are upgrading from a previous version of MBAM, you must use the same database name as the name that was used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e98ab-151">讀/寫存取網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="e98ab-151">Read/write access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-152">擁有此資料庫讀/寫許可權的網域使用者或群組，可讓 web 應用程式存取此資料庫中的資料和報表。</span><span class="sxs-lookup"><span data-stu-id="e98ab-152">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span></p>
   <p><span data-ttu-id="e98ab-153">如果您在此欄位中輸入使用者，其值必須與 <strong> </strong> [ <strong> 設定 web 應用程式] 頁面上的 [web 服務應用程式池網域帳戶] 欄位中的值相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e98ab-153">If you enter a user in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
   <p><span data-ttu-id="e98ab-154">如果您在此欄位中輸入群組，則 [ <strong> 設定 Web 應用程式] 頁面上的 [Web 服務應用程式群組網域帳戶] 欄位中的值 </strong> <strong> </strong> 必須是您在這個欄位中輸入之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e98ab-154">If you enter a group in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e98ab-155">唯讀存取網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="e98ab-155">Read-only access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-156">將對此資料庫擁有唯讀許可權的使用者或群組的名稱，以讓報告能夠存取此資料庫中的合規性資料。</span><span class="sxs-lookup"><span data-stu-id="e98ab-156">Name of the user or group that will have read-only permission to this database to enable the reports to access the compliance data in this database.</span></span></p>
   <p><span data-ttu-id="e98ab-157">如果您在此欄位中輸入使用者，該使用者必須是您在 <strong> </strong> [設定報告] 頁面上的 [合規性和審核資料庫網域帳戶] 欄位中所指定的使用者 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e98ab-157">If you enter a user in this field, it must be the same user as the one you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page.</span></span></p>
   <p><span data-ttu-id="e98ab-158">如果您在此欄位中輸入群組，您在 <strong> [設定報告] 頁面上的 [合規性與審計資料庫網域帳戶] 欄位中所指定的值， </strong> <strong> </strong> 必須是您在此欄位中指定之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e98ab-158">If you enter a group in this field, the value that you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page must be a member of the group that you specify in this field.</span></span></p></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="e98ab-159">請繼續閱讀下一節，以設定復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="e98ab-159">Continue to the next section to configure the Recovery Database.</span></span>

**<span data-ttu-id="e98ab-160">使用嚮導來設定恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="e98ab-160">To configure the Recovery Database by using the wizard</span></span>**

1. <span data-ttu-id="e98ab-161">使用下列說明，在嚮導中輸入欄位值：</span><span class="sxs-lookup"><span data-stu-id="e98ab-161">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e98ab-162">欄位</span><span class="sxs-lookup"><span data-stu-id="e98ab-162">Field</span></span></th>
   <th align="left"><span data-ttu-id="e98ab-163">描述</span><span class="sxs-lookup"><span data-stu-id="e98ab-163">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e98ab-164">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="e98ab-164">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-165">您正在設定復原資料庫的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-165">Name of the server where you are configuring the Recovery Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e98ab-166">注意</span><span class="sxs-lookup"><span data-stu-id="e98ab-166">Note</span></span></strong><br/><p><span data-ttu-id="e98ab-167">您必須在恢復資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。</span><span class="sxs-lookup"><span data-stu-id="e98ab-167">You must add an exception on the Recovery Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="e98ab-168">預設埠號碼是1433。</span><span class="sxs-lookup"><span data-stu-id="e98ab-168">The default port number is 1433.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e98ab-169">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="e98ab-169">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-170">儲存恢復資料之資料庫實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-170">Name of the database instance where the recovery data will be stored.</span></span> <span data-ttu-id="e98ab-171">您也必須指定資料庫資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="e98ab-171">You must also specify where the database information will be located.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e98ab-172">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="e98ab-172">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-173">儲存修復資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-173">Name of the database that will store the recovery data.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e98ab-174">注意</span><span class="sxs-lookup"><span data-stu-id="e98ab-174">Note</span></span></strong><br/><p><span data-ttu-id="e98ab-175">如果您是從舊版 MBAM 升級，您必須使用與先前部署中所使用的名稱相同的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="e98ab-175">If you are upgrading from a previous version of MBAM, you must use the same database name as the name that was used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e98ab-176">讀/寫存取網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="e98ab-176">Read/write access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e98ab-177">擁有此資料庫讀/寫許可權的網域使用者或群組，可讓 web 應用程式存取此資料庫中的資料和報表。</span><span class="sxs-lookup"><span data-stu-id="e98ab-177">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span></p>
   <p><span data-ttu-id="e98ab-178">如果您在此欄位中輸入使用者，其值必須與 <strong> </strong> [ <strong> 設定 web 應用程式] 頁面上的 [web 服務應用程式池網域帳戶] 欄位中的值相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e98ab-178">If you enter a user in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
   <p><span data-ttu-id="e98ab-179">如果您在此欄位中輸入群組，則 [ <strong> 設定 Web 應用程式] 頁面上的 [Web 服務應用程式群組網域帳戶] 欄位中的值 </strong> <strong> </strong> 必須是您在這個欄位中輸入之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e98ab-179">If you enter a group in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="e98ab-180">完成專案後，請按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="e98ab-180">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="e98ab-181">嚮導會檢查資料庫的所有先決條件是否都已滿足。</span><span class="sxs-lookup"><span data-stu-id="e98ab-181">The wizard checks that all prerequisites for the databases have been met.</span></span>

3. <span data-ttu-id="e98ab-182">如果先決條件檢查成功，請按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="e98ab-182">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="e98ab-183">否則，請解決任何缺少的先決條件，然後再按**一次 [下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="e98ab-183">Otherwise, resolve any missing prerequisites, and then click **Next** again.</span></span>

4. <span data-ttu-id="e98ab-184">在 [**摘要**] 頁面上，查看將新增的功能。</span><span class="sxs-lookup"><span data-stu-id="e98ab-184">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="e98ab-185">注意</span><span class="sxs-lookup"><span data-stu-id="e98ab-185">Note</span></span>**  
   <span data-ttu-id="e98ab-186">若要建立您剛剛建立之專案的 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**]，然後儲存腳本。</span><span class="sxs-lookup"><span data-stu-id="e98ab-186">To create a Windows PowerShell script of the entries that you just made, click **Export PowerShell Script**, and then save the script.</span></span>



5. <span data-ttu-id="e98ab-187">按一下 [**新增**]，在伺服器上新增 MBAM 資料庫，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e98ab-187">Click **Add** to add the MBAM databases on the server, and then click **Close**.</span></span>



## <span data-ttu-id="e98ab-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="e98ab-188">Related topics</span></span>


[<span data-ttu-id="e98ab-189">伺服器事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="e98ab-189">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="e98ab-190">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="e98ab-190">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="e98ab-191">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="e98ab-191">How to Configure the MBAM 2.5 Reports</span></span>](how-to-configure-the-mbam-25-reports.md)

[<span data-ttu-id="e98ab-192">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="e98ab-192">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="e98ab-193">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="e98ab-193">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)



## <span data-ttu-id="e98ab-194">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="e98ab-194">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e98ab-195">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="e98ab-195">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="e98ab-196">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e98ab-196">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





