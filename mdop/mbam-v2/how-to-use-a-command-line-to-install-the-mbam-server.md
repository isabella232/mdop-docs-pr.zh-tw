---
title: 如何使用命令列安裝 MBAM 伺服器
description: 如何使用命令列安裝 MBAM 伺服器
author: dansimp
ms.assetid: 6ffc6d41-a793-42c2-b997-95ba47550648
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a689a2df77300300073b2731281004feac87305f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811277"
---
# <span data-ttu-id="50225-103">如何使用命令列安裝 MBAM 伺服器</span><span class="sxs-lookup"><span data-stu-id="50225-103">How to Use a Command Line to Install the MBAM Server</span></span>


<span data-ttu-id="50225-104">您可以使用命令列，透過獨立或 Configuration Manager 拓撲來安裝 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="50225-104">You can use a command line to install the MBAM Server with either the Stand-alone or Configuration Manager topology.</span></span> <span data-ttu-id="50225-105">下列命令列範例是用於在單一伺服器上部署 MBAM，這是一個只能在測試環境中使用的架構。</span><span class="sxs-lookup"><span data-stu-id="50225-105">The following command line example is for deploying MBAM on a single server, which is an architecture that should be used only in a test environment.</span></span> <span data-ttu-id="50225-106">當您將 MBAM 部署至生產環境時，您需要變更命令列，這應該有多個伺服器。</span><span class="sxs-lookup"><span data-stu-id="50225-106">You will need to change the command line accordingly when you deploy MBAM to a production environment, which should have multiple servers.</span></span>

## <span data-ttu-id="50225-107">用獨立拓朴部署 MBAM 2.0 伺服器的命令列</span><span class="sxs-lookup"><span data-stu-id="50225-107">Command Line for Deploying the MBAM2.0 Server with the Stand-alone Topology</span></span>


<span data-ttu-id="50225-108">您可以使用類似下列的命令列，以獨立拓朴來安裝 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="50225-108">You can use a command line that is similar to the following to install the MBAM Server with the Stand-alone topology.</span></span>

``` syntax
MbamSetup.exe /qb /l*v MaltaServerInstall.log TOPOLOGY=0 I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 ADDLOCAL=KeyDatabase,ReportsDatabase,Reports,AdministrationMonitoringServer,SelfServiceServer,PolicyTemplate,REPORTS_USERACCOUNT=[UserDomain]\[UserName1] REPORTS_USERACCOUNTPW=[UserPwd1] COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

<span data-ttu-id="50225-109">下表說明用獨立拓朴部署 MBAM 伺服器的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="50225-109">The following table describes the command line parameters for deploying the MBAM Server with the Stand-alone topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="50225-110">參數</span><span class="sxs-lookup"><span data-stu-id="50225-110">Parameter</span></span></th>
<th align="left"><span data-ttu-id="50225-111">參數值</span><span class="sxs-lookup"><span data-stu-id="50225-111">Parameter Value</span></span></th>
<th align="left"><span data-ttu-id="50225-112">描述</span><span class="sxs-lookup"><span data-stu-id="50225-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-113">技術</span><span class="sxs-lookup"><span data-stu-id="50225-113">TOPOLOGY</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-114">0</span><span class="sxs-lookup"><span data-stu-id="50225-114">0</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-115">0–獨立拓朴</span><span class="sxs-lookup"><span data-stu-id="50225-115">0 – Stand-alone topology</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-116">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span><span class="sxs-lookup"><span data-stu-id="50225-116">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-117">01</span><span class="sxs-lookup"><span data-stu-id="50225-117">01</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-118">0–不接受授權 agreement1 –接受授權協定</span><span class="sxs-lookup"><span data-stu-id="50225-118">0 – do not accept the license agreement1 – accept the license agreement</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-119">ADDLOCAL</span><span class="sxs-lookup"><span data-stu-id="50225-119">ADDLOCAL</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-120">要在伺服器上安裝的功能</span><span class="sxs-lookup"><span data-stu-id="50225-120">Features to be installed on the Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-121">KeyDatabase</span><span class="sxs-lookup"><span data-stu-id="50225-121">KeyDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-122">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="50225-122">Recovery Database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-123">ReportsDatabase</span><span class="sxs-lookup"><span data-stu-id="50225-123">ReportsDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-124">合規性和審核報告資料庫</span><span class="sxs-lookup"><span data-stu-id="50225-124">Compliance and Audit Reports Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-125">報告</span><span class="sxs-lookup"><span data-stu-id="50225-125">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-126">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="50225-126">Compliance and Audit Reports</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-127">AdministrationMonitoringServer</span><span class="sxs-lookup"><span data-stu-id="50225-127">AdministrationMonitoringServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-128">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="50225-128">Administration and Monitoring website</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-129">SelfServiceServer</span><span class="sxs-lookup"><span data-stu-id="50225-129">SelfServiceServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-130">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="50225-130">Self-Service Portal</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="50225-131">PolicyTemplate</span><span class="sxs-lookup"><span data-stu-id="50225-131">PolicyTemplate</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-132">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="50225-132">MBAM Group Policy template</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-133">REPORTS_USERACCOUNT</span><span class="sxs-lookup"><span data-stu-id="50225-133">REPORTS_USERACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-134">[UserDomain][UserName1]</span><span class="sxs-lookup"><span data-stu-id="50225-134">[UserDomain][UserName1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-135">可存取合規性和審核資料庫之 Reporting Services 服務帳戶的網域和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="50225-135">Domain and user account of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-136">REPORTS_USERACCOUNTPW</span><span class="sxs-lookup"><span data-stu-id="50225-136">REPORTS_USERACCOUNTPW</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-137">[UserPwd1]</span><span class="sxs-lookup"><span data-stu-id="50225-137">[UserPwd1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-138">可存取合規性和審核資料庫之 Reporting Services 服務帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="50225-138">Password of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-139">COMPLIDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="50225-139">COMPLIDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-140">名稱</span><span class="sxs-lookup"><span data-stu-id="50225-140">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-141">合規性和審核資料庫的 SQL Server 實例名稱– <strong> 將% computername% 替換 </strong> 為電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="50225-141">SQL Server instance name for the Compliance and Audit Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-142">RECOVERYANDHWDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="50225-142">RECOVERYANDHWDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-143">名稱</span><span class="sxs-lookup"><span data-stu-id="50225-143">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-144">針對復原資料庫的 SQL Server 實例名稱– <strong> 將% computername% 替換 </strong> 為電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="50225-144">SQL Server instance name for the Recovery Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-145">SRS_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="50225-145">SRS_INSTANCENAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-146">名稱</span><span class="sxs-lookup"><span data-stu-id="50225-146">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-147">要安裝合規性和審核報告的 SQL Server Reporting Server 實例–將 <strong> % computername% 替換 </strong> 為電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="50225-147">SQL Server Reporting Server instance where the Compliance and Audit reports will be installed – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-148">ADMINANDMON_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="50225-148">ADMINANDMON_WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-149">83</span><span class="sxs-lookup"><span data-stu-id="50225-149">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-150">管理和監視網站的埠;"83" 只是範例</span><span class="sxs-lookup"><span data-stu-id="50225-150">Port for the Administration and Monitoring website; “83” is only an example</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-151">WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="50225-151">WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-152">83</span><span class="sxs-lookup"><span data-stu-id="50225-152">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-153">自助服務入口網站的埠;"83" 只是範例</span><span class="sxs-lookup"><span data-stu-id="50225-153">Port for the Self-Service Portal website; “83” is only an example</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="50225-154">用 Configuration Manager 拓撲部署 MBAM 2.0 伺服器的命令列</span><span class="sxs-lookup"><span data-stu-id="50225-154">Command Line for Deploying the MBAM2.0 Server with the Configuration Manager Topology</span></span>


<span data-ttu-id="50225-155">您可以使用類似下列的命令列來安裝 MBAM 伺服器與 Configuration Manager 拓撲。</span><span class="sxs-lookup"><span data-stu-id="50225-155">You can use a command line that is similar to the following to install the MBAM Server with the Configuration Manager topology.</span></span>

``` syntax
MbamSetup.exe /qn /l*v MaltaServerInstall.log I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 TOPOLOGY=1 COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% REPORTS_USERACCOUNT=[UserDomain]\[UserName] REPORTS_USERACCOUNTPW=[UserPwd] ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

<span data-ttu-id="50225-156">下表說明用 Configuration Manager 拓撲來安裝 MBAM 2.0 伺服器的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="50225-156">The following table describes the command line parameters for installing the MBAM2.0 Server with the Configuration Manager topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="50225-157">參數</span><span class="sxs-lookup"><span data-stu-id="50225-157">Parameter</span></span></th>
<th align="left"><span data-ttu-id="50225-158">參數值</span><span class="sxs-lookup"><span data-stu-id="50225-158">Parameter Value</span></span></th>
<th align="left"><span data-ttu-id="50225-159">描述</span><span class="sxs-lookup"><span data-stu-id="50225-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-160">技術</span><span class="sxs-lookup"><span data-stu-id="50225-160">TOPOLOGY</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-161">sr-1</span><span class="sxs-lookup"><span data-stu-id="50225-161">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-162">1-Configuration Manager 拓撲</span><span class="sxs-lookup"><span data-stu-id="50225-162">1 – Configuration Manager topology</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-163">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span><span class="sxs-lookup"><span data-stu-id="50225-163">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-164">01</span><span class="sxs-lookup"><span data-stu-id="50225-164">01</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-165">0–不接受授權 agreement1 –接受授權協定</span><span class="sxs-lookup"><span data-stu-id="50225-165">0 – do not accept the license agreement1 – accept the license agreement</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-166">COMPLIDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="50225-166">COMPLIDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-167">名稱</span><span class="sxs-lookup"><span data-stu-id="50225-167">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-168">審核資料庫的 SQL Server 實例名稱– <strong> 將% computername% 替換 </strong> 為電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="50225-168">SQL Server instance name for the Audit Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-169">RECOVERYANDHWDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="50225-169">RECOVERYANDHWDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-170">名稱</span><span class="sxs-lookup"><span data-stu-id="50225-170">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-171">恢復資料庫的 SQL Server 實例名稱- <strong> </strong> 以電腦名稱稱取代% computername%</span><span class="sxs-lookup"><span data-stu-id="50225-171">SQL Server instance name for the Recovery Database - replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-172">SRS_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="50225-172">SRS_INSTANCENAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-173">名稱</span><span class="sxs-lookup"><span data-stu-id="50225-173">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-174">要安裝審計報告的 SQL Server Reporting Server 實例–將% computername% 替換為電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="50225-174">SQL Server Reporting Server instance where the Audit reports will be installed – replace %computername% with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-175">REPORTS_USERACCOUNT</span><span class="sxs-lookup"><span data-stu-id="50225-175">REPORTS_USERACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-176">[UserDomain][UserName1]</span><span class="sxs-lookup"><span data-stu-id="50225-176">[UserDomain][UserName1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-177">可存取合規性和審核資料庫之 Reporting Services 服務帳戶的網域和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="50225-177">Domain and user account of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-178">REPORTS_USERACCOUNTPW</span><span class="sxs-lookup"><span data-stu-id="50225-178">REPORTS_USERACCOUNTPW</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-179">[UserPwd1]</span><span class="sxs-lookup"><span data-stu-id="50225-179">[UserPwd1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-180">可存取合規性和審核資料庫之 Reporting Services 服務帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="50225-180">Password of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50225-181">ADMINANDMON_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="50225-181">ADMINANDMON_WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-182">83</span><span class="sxs-lookup"><span data-stu-id="50225-182">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-183">管理和監視網站的埠;"83" 只是範例</span><span class="sxs-lookup"><span data-stu-id="50225-183">Port for the Administration and Monitoring website; “83” is only an example</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50225-184">WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="50225-184">WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-185">83</span><span class="sxs-lookup"><span data-stu-id="50225-185">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="50225-186">自助服務入口網站的埠;"83" 只是範例</span><span class="sxs-lookup"><span data-stu-id="50225-186">Port for the Self-Service Portal website; “83” is only an example</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="50225-187">相關主題</span><span class="sxs-lookup"><span data-stu-id="50225-187">Related topics</span></span>


[<span data-ttu-id="50225-188">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="50225-188">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





