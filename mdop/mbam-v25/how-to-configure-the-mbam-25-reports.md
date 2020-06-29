---
title: 如何設定 MBAM 2.5 報告
description: 如何設定 MBAM 2.5 報告
author: dansimp
ms.assetid: ec462879-0253-4d9c-83c7-a9bcad479725
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b372bd6bc38a3729aef43354ecf19b2619b7856
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811864"
---
# <span data-ttu-id="61a3d-103">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="61a3d-103">How to Configure the MBAM 2.5 Reports</span></span>


<span data-ttu-id="61a3d-104">本主題說明如何使用以下內容來設定 Microsoft BitLocker 管理和監控（MBAM）2.5 報告功能：</span><span class="sxs-lookup"><span data-stu-id="61a3d-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Reports feature by using:</span></span>

-   <span data-ttu-id="61a3d-105">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="61a3d-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="61a3d-106">[MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="61a3d-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="61a3d-107">指示是以[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)中的建議架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="61a3d-107">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="61a3d-108">開始設定前：</span><span class="sxs-lookup"><span data-stu-id="61a3d-108">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="61a3d-109">步驟</span><span class="sxs-lookup"><span data-stu-id="61a3d-109">Step</span></span></th>
<th align="left"><span data-ttu-id="61a3d-110">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="61a3d-110">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61a3d-111">針對 MBAM 查看建議的架構。</span><span class="sxs-lookup"><span data-stu-id="61a3d-111">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="61a3d-112">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="61a3d-112">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61a3d-113">查看 MBAM 支援的設定。</span><span class="sxs-lookup"><span data-stu-id="61a3d-113">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="61a3d-114">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="61a3d-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61a3d-115">在每個伺服器上完成必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="61a3d-115">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="61a3d-116">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="61a3d-116">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="61a3d-117">僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 必備元件 </a> （如果適用）</span><span class="sxs-lookup"><span data-stu-id="61a3d-117">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61a3d-118">在您規劃設定 MBAM 伺服器功能的每個伺服器上，安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="61a3d-118">Install the MBAM Server software on each server where you plan to configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="61a3d-119">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="61a3d-119">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61a3d-120">如果您打算使用 Windows powershell Cmdlet 來設定 MBAM 伺服器功能，請參閱使用 Windows PowerShell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="61a3d-120">Review the prerequisites for using Windows PowerShell if you plan to use Windows PowerShell cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="61a3d-121">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="61a3d-121">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="61a3d-122">使用 Windows PowerShell 來設定報表</span><span class="sxs-lookup"><span data-stu-id="61a3d-122">To configure the Reports by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="61a3d-123">開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="61a3d-123">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="61a3d-124">使用**Enable-MbamReport** Windows PowerShell Cmdlet 來設定報告。</span><span class="sxs-lookup"><span data-stu-id="61a3d-124">Use the **Enable-MbamReport** Windows PowerShell cmdlet to configure the Reports.</span></span> <span data-ttu-id="61a3d-125">若要取得有關這個 Windows PowerShell Cmdlet 的資訊，請輸入**Get-help Enable-MbamReport**。</span><span class="sxs-lookup"><span data-stu-id="61a3d-125">To get information about this Windows PowerShell cmdlet, type **Get-Help Enable-MbamReport**.</span></span>

**<span data-ttu-id="61a3d-126">使用嚮導來設定報表</span><span class="sxs-lookup"><span data-stu-id="61a3d-126">To configure the Reports by using the wizard</span></span>**

1. <span data-ttu-id="61a3d-127">在您想要設定報告的伺服器上，啟動 [ **MBAM 伺服器**設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="61a3d-127">On the server where you want to configure the Reports, start the **MBAM Server Configuration** wizard.</span></span> <span data-ttu-id="61a3d-128">您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。</span><span class="sxs-lookup"><span data-stu-id="61a3d-128">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="61a3d-129">按一下 [**新增功能**]，選取 [**報表**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="61a3d-129">Click **Add New Features**, select **Reports**, and then click **Next**.</span></span> <span data-ttu-id="61a3d-130">嚮導會檢查是否符合報表的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="61a3d-130">The wizard checks that all prerequisites for the Reports have been met.</span></span>

3. <span data-ttu-id="61a3d-131">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="61a3d-131">Click **Next** to continue.</span></span>

4. <span data-ttu-id="61a3d-132">使用下列說明，在嚮導中輸入欄位值：</span><span class="sxs-lookup"><span data-stu-id="61a3d-132">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="61a3d-133">欄位</span><span class="sxs-lookup"><span data-stu-id="61a3d-133">Field</span></span></th>
   <th align="left"><span data-ttu-id="61a3d-134">描述</span><span class="sxs-lookup"><span data-stu-id="61a3d-134">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="61a3d-135">SQL Server Reporting Services 實例</span><span class="sxs-lookup"><span data-stu-id="61a3d-135">SQL Server Reporting Services instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="61a3d-136">將設定報告的 SQL Server Reporting Services 實例。</span><span class="sxs-lookup"><span data-stu-id="61a3d-136">Instance of SQL Server Reporting Services where the Reports will be configured.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="61a3d-137">報告角色網域群組</span><span class="sxs-lookup"><span data-stu-id="61a3d-137">Reporting role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="61a3d-138">其成員有權存取管理和監視伺服器上報告的網域使用者群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="61a3d-138">Name of the domain Users group whose members have rights to access the reports on the Administration and Monitoring Server.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="61a3d-139">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="61a3d-139">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="61a3d-140">已設定合規性和審核資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="61a3d-140">Name of the server where the Compliance and Audit Database is configured.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="61a3d-141">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="61a3d-141">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="61a3d-142">在 <em> </em> 其中設定合規性和審核資料庫之 SQL Server 實例（例如，MSSQLSERVER）的名稱。</span><span class="sxs-lookup"><span data-stu-id="61a3d-142">Name of the instance of SQL Server (for example, <em>MSSQLSERVER</em>) where the Compliance and Audit Database is configured.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="61a3d-143">注意</span><span class="sxs-lookup"><span data-stu-id="61a3d-143">Note</span></span></strong><br/><p><span data-ttu-id="61a3d-144">您必須在報表電腦上新增例外狀況，才能在報表伺服器的埠上啟用輸入流量（預設埠為80）。</span><span class="sxs-lookup"><span data-stu-id="61a3d-144">You must add an exception on the Reports computer to enable inbound traffic on the port of the Reporting Server (the default port is 80).</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="61a3d-145">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="61a3d-145">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="61a3d-146">合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="61a3d-146">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="61a3d-147">根據預設，資料庫名稱是 <strong> MBAM 合規性狀態 </strong> ，不過您可以在設定合規性和審核資料庫時變更名稱。</span><span class="sxs-lookup"><span data-stu-id="61a3d-147">By default, the database name is <strong>MBAM Compliance Status</strong>, although you can change the name when you configure the Compliance and Audit Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="61a3d-148">注意</span><span class="sxs-lookup"><span data-stu-id="61a3d-148">Note</span></span></strong><br/><p><span data-ttu-id="61a3d-149">如果您是從舊版 MBAM 升級，您必須使用與先前部署中所使用之名稱相同的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="61a3d-149">If you are upgrading from a previous version of MBAM, you must use the same database name as the name used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="61a3d-150">合規性與審計資料庫網域帳戶</span><span class="sxs-lookup"><span data-stu-id="61a3d-150">Compliance and Audit Database domain account</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="61a3d-151">[網域使用者帳戶和密碼] 來存取合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="61a3d-151">Domain user account and password to access the Compliance and Audit Database.</span></span></p>
   <p><span data-ttu-id="61a3d-152">如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是使用者，則您必須在這個欄位中輸入相同的值。</span><span class="sxs-lookup"><span data-stu-id="61a3d-152">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a user, you must enter that same value in this field.</span></span></p>
   <p><span data-ttu-id="61a3d-153">如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是群組，則您在這個欄位中輸入的值必須是該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="61a3d-153">If the value that you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a group, the value that you enter in this field must be a member of that group.</span></span></p>
   <p><span data-ttu-id="61a3d-154">將此帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="61a3d-154">Configure the password for this account to never expire.</span></span> <span data-ttu-id="61a3d-155">使用者帳戶應該能夠存取 MBAM [報告使用者] 群組提供的所有資料。</span><span class="sxs-lookup"><span data-stu-id="61a3d-155">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span></p></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="61a3d-156">完成專案後，請按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="61a3d-156">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="61a3d-157">嚮導會檢查是否已符合報表功能的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="61a3d-157">The wizard checks that all prerequisites for the Reports feature have been met.</span></span>

6. <span data-ttu-id="61a3d-158">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="61a3d-158">Click **Next** to continue.</span></span>

7. <span data-ttu-id="61a3d-159">在 [**摘要**] 頁面上，查看將新增的功能。</span><span class="sxs-lookup"><span data-stu-id="61a3d-159">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="61a3d-160">注意</span><span class="sxs-lookup"><span data-stu-id="61a3d-160">Note</span></span>**  
   <span data-ttu-id="61a3d-161">若要建立您剛剛建立之專案的 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**]，然後儲存腳本。</span><span class="sxs-lookup"><span data-stu-id="61a3d-161">To create a Windows PowerShell script of the entries that you just made, click **Export PowerShell Script**, and then save the script.</span></span>



8. <span data-ttu-id="61a3d-162">按一下 [**新增**]，在伺服器上新增報表，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="61a3d-162">Click **Add** to add the Reports on the server, and then click **Close**.</span></span>



## <span data-ttu-id="61a3d-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="61a3d-163">Related topics</span></span>


[<span data-ttu-id="61a3d-164">伺服器事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="61a3d-164">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="61a3d-165">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="61a3d-165">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="61a3d-166">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="61a3d-166">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="61a3d-167">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="61a3d-167">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)


## <span data-ttu-id="61a3d-168">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="61a3d-168">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="61a3d-169">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="61a3d-169">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="61a3d-170">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="61a3d-170">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






