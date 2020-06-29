---
title: 獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
description: 獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
author: dansimp
ms.assetid: 76a6047a-5c6e-42ff-af09-a6f382a69537
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9af551b1d867f61912bbf3b759574a840b0645c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811492"
---
# <span data-ttu-id="4de18-103">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="4de18-103">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>


<span data-ttu-id="4de18-104">開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您必須完成本主題中所列的先決條件。</span><span class="sxs-lookup"><span data-stu-id="4de18-104">Before starting the Microsoft BitLocker Administration and Monitoring (MBAM) installation, you must complete the prerequisites listed in this topic.</span></span> <span data-ttu-id="4de18-105">這些先決條件適用于 MBAM 獨立拓朴與 System Center Configuration Manager 整合拓撲。</span><span class="sxs-lookup"><span data-stu-id="4de18-105">These prerequisites apply to the MBAM Stand-alone topology and System Center Configuration Manager Integration topology.</span></span>

<span data-ttu-id="4de18-106">如果您是使用 System Center Configuration Manager 部署 MBAM，您必須完成其他先決條件，這些必備元件會列在[僅適用于 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必備元件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)中。</span><span class="sxs-lookup"><span data-stu-id="4de18-106">If you are deploying MBAM with System Center Configuration Manager, you must complete additional prerequisites, which are listed in [MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md).</span></span>

<span data-ttu-id="4de18-107">如需 MBAM 支援的硬體與作業系統清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="4de18-107">For a list of the supported hardware and operating systems for MBAM, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

**<span data-ttu-id="4de18-108">重要</span><span class="sxs-lookup"><span data-stu-id="4de18-108">Important</span></span>**  
<span data-ttu-id="4de18-109">如果使用的是沒有 MBAM 的 BitLocker，您必須解密磁片磁碟機，然後使用 [雲端] 清除 TPM。</span><span class="sxs-lookup"><span data-stu-id="4de18-109">If BitLocker was used without MBAM, you must decrypt the drive and then clear TPM using tpm.msc.</span></span> <span data-ttu-id="4de18-110">如果用戶端電腦已加密，且已建立 TPM 擁有者密碼，則 MBAM 無法取得 TPM 的擁有權。</span><span class="sxs-lookup"><span data-stu-id="4de18-110">MBAM cannot take ownership of TPM if the client PC is already encrypted and the TPM owner password created.</span></span>



## <span data-ttu-id="4de18-111">必要的 MBAM 角色和帳戶</span><span class="sxs-lookup"><span data-stu-id="4de18-111">Required MBAM roles and accounts</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-112">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-112">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-114">在 Active Directory 網域服務（AD DS）中建立的群組</span><span class="sxs-lookup"><span data-stu-id="4de18-114">Groups created in Active Directory Domain Services (AD DS)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-115"><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"> </a> 如需這些群組和帳戶的描述，請參閱規劃 MBAM 2.5 群組和帳戶。</span><span class="sxs-lookup"><span data-stu-id="4de18-115">See <a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)">Planning for MBAM 2.5 Groups and Accounts</a> for a description of these groups and accounts.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4de18-116">恢復資料庫的先決條件</span><span class="sxs-lookup"><span data-stu-id="4de18-116">Prerequisites for the Recovery Database</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-117">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-117">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-118">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-118">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-119">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="4de18-119">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-120">使用 SQL_Latin1_General_CP1_CI_AS 的排序規則安裝 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4de18-120">Install Microsoft SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="4de18-121"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="4de18-121">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-122">必要的 SQL Server 許可權</span><span class="sxs-lookup"><span data-stu-id="4de18-122">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-123">所需的許可權：</span><span class="sxs-lookup"><span data-stu-id="4de18-123">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-124">SQL Server 實例登入伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="4de18-124">SQL Server instance login server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-125">dbcreator</span><span class="sxs-lookup"><span data-stu-id="4de18-125">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="4de18-126">processadmin</span><span class="sxs-lookup"><span data-stu-id="4de18-126">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="4de18-127">SQL Server Reporting Services 實例許可權：</span><span class="sxs-lookup"><span data-stu-id="4de18-127">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-128">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="4de18-128">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="4de18-129">發佈報表</span><span class="sxs-lookup"><span data-stu-id="4de18-129">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-130">選用-安裝 SQL Server 提供的透明資料加密（TDE）功能</span><span class="sxs-lookup"><span data-stu-id="4de18-130">Optional - Install the Transparent Data Encryption (TDE) feature available in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-131">TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守適用于各種行業的法律、規章及指導方針。</span><span class="sxs-lookup"><span data-stu-id="4de18-131">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with laws, regulations, and guidelines that apply to various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4de18-132">注意</span><span class="sxs-lookup"><span data-stu-id="4de18-132">Note</span></span></strong><br/><p><span data-ttu-id="4de18-133">TDE 執行資料庫資訊的即時解密。</span><span class="sxs-lookup"><span data-stu-id="4de18-133">TDE performs real-time decryption of database information.</span></span> <span data-ttu-id="4de18-134">這表示如果您是在 SQL Server 資料庫中查看復原金鑰資訊，而且您是以擁有資料庫許可權的帳戶登入，則會看到 [復原金鑰資訊]。</span><span class="sxs-lookup"><span data-stu-id="4de18-134">This means that, if you are viewing recovery key information in the SQL Server database and you are logged on under an account that has permissions to the database, the recovery key information is visible.</span></span> <span data-ttu-id="4de18-135">若要深入瞭解 TDE，請參閱 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全性考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4de18-135">To read more about TDE, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-136">SQL Server 資料庫引擎服務</span><span class="sxs-lookup"><span data-stu-id="4de18-136">SQL Server Database Engine Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-137">在安裝 MBAM 伺服器期間，必須安裝並執行 SQL Server 資料庫引擎服務。</span><span class="sxs-lookup"><span data-stu-id="4de18-137">SQL Server Database Engine Services must be installed and running during MBAM Server installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-138">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4de18-138">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-139">如果您使用 Windows PowerShell 從遠端電腦設定資料庫，就不需要在恢復資料庫伺服器上安裝 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4de18-139">Windows PowerShell does not have to be installed on the Recovery Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4de18-140">合規性和審核資料庫的先決條件</span><span class="sxs-lookup"><span data-stu-id="4de18-140">Prerequisites for the Compliance and Audit Database</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-141">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-141">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-142">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-142">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-143">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="4de18-143">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-144">安裝含有 SQL_Latin1_General_CP1_CI_AS 排序規則的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4de18-144">Install SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="4de18-145"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="4de18-145">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-146">必要的 SQL Server 許可權</span><span class="sxs-lookup"><span data-stu-id="4de18-146">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-147">所需的許可權：</span><span class="sxs-lookup"><span data-stu-id="4de18-147">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-148">SQL Server 實例登入伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="4de18-148">SQL Server instance login server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-149">dbcreator</span><span class="sxs-lookup"><span data-stu-id="4de18-149">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="4de18-150">processadmin</span><span class="sxs-lookup"><span data-stu-id="4de18-150">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="4de18-151">SQL Server Reporting Services 實例許可權：</span><span class="sxs-lookup"><span data-stu-id="4de18-151">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-152">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="4de18-152">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="4de18-153">發佈報表</span><span class="sxs-lookup"><span data-stu-id="4de18-153">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-154">選用-在 SQL Server 中安裝透明資料加密（TDE）功能</span><span class="sxs-lookup"><span data-stu-id="4de18-154">Optional - Install the Transparent Data Encryption (TDE) feature in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-155">TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守適用于各種行業的法律、規章及指導方針。</span><span class="sxs-lookup"><span data-stu-id="4de18-155">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with laws, regulations, and guidelines that apply to various industries.</span></span></p>
<p><span data-ttu-id="4de18-156">TDE 執行資料庫資訊的即時解密。</span><span class="sxs-lookup"><span data-stu-id="4de18-156">TDE performs real-time decryption of database information.</span></span> <span data-ttu-id="4de18-157">這表示如果您是在 SQL Server 資料庫中查看復原金鑰資訊，而且您是以擁有資料庫許可權的帳戶登入，則會看到 [復原金鑰資訊]。</span><span class="sxs-lookup"><span data-stu-id="4de18-157">This means that, if you are viewing recovery key information in the SQL Server database and you are logged on under an account that has permissions to the database, the recovery key information is visible.</span></span> <span data-ttu-id="4de18-158">若要深入瞭解 TDE，請參閱 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全性考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4de18-158">To read more about TDE, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-159">SQL Server 資料庫引擎服務</span><span class="sxs-lookup"><span data-stu-id="4de18-159">SQL Server Database Engine Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-160">在安裝 MBAM 伺服器期間，必須安裝並執行 SQL Server 資料庫引擎服務。</span><span class="sxs-lookup"><span data-stu-id="4de18-160">SQL Server Database Engine Services must be installed and running during MBAM Server installation.</span></span> <span data-ttu-id="4de18-161">不過，您可以在遠端執行 SQL Server;它不一定要在您安裝 MBAM Server 軟體的同一個伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4de18-161">However, SQL Server can be running remotely; it doesn’t have to be on the same server on which you are installing the MBAM Server software.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-162">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4de18-162">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-163">如果您使用 Windows PowerShell 從遠端電腦設定資料庫，就不需要在合規性和審核資料庫伺服器上安裝 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4de18-163">Windows PowerShell does not have to be installed on the Compliance and Audit Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4de18-164">報表的先決條件</span><span class="sxs-lookup"><span data-stu-id="4de18-164">Prerequisites for the Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-165">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-165">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-166">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-166">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-167">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="4de18-167">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-168">安裝含有 SQL_Latin1_General_CP1_CI_AS 排序規則的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4de18-168">Install SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="4de18-169"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="4de18-169">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-170">SQL Server Reporting Services （SSRS）</span><span class="sxs-lookup"><span data-stu-id="4de18-170">SQL Server Reporting Services (SSRS)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-171">在安裝 MBAM 伺服器期間，必須安裝並執行 SSRS。</span><span class="sxs-lookup"><span data-stu-id="4de18-171">SSRS must be installed and running during the MBAM Server installation.</span></span></p>
<p><span data-ttu-id="4de18-172">在純模式中設定 SSRS &quot; &quot; ，而不是在未設定或 &quot; SharePoint 模式中進行 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="4de18-172">Configure SSRS in &quot;native&quot; mode and not in unconfigured or &quot;SharePoint&quot; mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-173">SSRS 實例許可權–只有當您在已設定報表的伺服器上安裝資料庫時，才能配置報表。</span><span class="sxs-lookup"><span data-stu-id="4de18-173">SSRS instance rights – required for configuring Reports only if you are installing databases on a separate server from the server where Reports are configured.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-174">所需的實例許可權：</span><span class="sxs-lookup"><span data-stu-id="4de18-174">Required instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="4de18-175">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="4de18-175">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="4de18-176">發佈報表</span><span class="sxs-lookup"><span data-stu-id="4de18-176">Publish Reports</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-177">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4de18-177">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-178">如果您使用 Windows PowerShell 從遠端電腦設定資料庫，就不需要在此資料庫伺服器上安裝 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4de18-178">Windows PowerShell does not have to be installed on this Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-prereqsams"></a><span data-ttu-id="4de18-179">管理和監視伺服器的先決條件</span><span class="sxs-lookup"><span data-stu-id="4de18-179">Prerequisites for the Administration and Monitoring Server</span></span>


<span data-ttu-id="4de18-180">下表列出 MBAM 管理和監視伺服器的安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="4de18-180">The following table lists the installation prerequisites for the MBAM Administration and Monitoring Server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-181">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-181">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-182">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-182">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-183">Windows Server Web Server 角色</span><span class="sxs-lookup"><span data-stu-id="4de18-183">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-184">這個角色必須新增至 [管理與監視伺服器] 功能支援的伺服器作業系統。</span><span class="sxs-lookup"><span data-stu-id="4de18-184">This role must be added to a server operating system that is supported for the Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-185">Web 服務器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="4de18-185">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-186">按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4de18-186">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4de18-187">SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="4de18-187">SSL Certificate</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4de18-188">選用。</span><span class="sxs-lookup"><span data-stu-id="4de18-188">Optional.</span></span> <span data-ttu-id="4de18-189">若要保護用戶端電腦與 web 服務之間的通訊，您必須取得並安裝受信任的安全機構已簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="4de18-189">To secure communication between the client computers and the web services, you must obtain and install a certificate that a trusted security authority signed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-190">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="4de18-190">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="4de18-191">常見的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="4de18-191">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="4de18-192">靜態內容</span><span class="sxs-lookup"><span data-stu-id="4de18-192">Static Content</span></span></p></li>
<li><p><span data-ttu-id="4de18-193">預設檔</span><span class="sxs-lookup"><span data-stu-id="4de18-193">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="4de18-194">應用程式開發：</span><span class="sxs-lookup"><span data-stu-id="4de18-194">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="4de18-195">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4de18-195">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="4de18-196">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="4de18-196">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="4de18-197">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="4de18-197">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="4de18-198">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="4de18-198">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="4de18-199">安全性</span><span class="sxs-lookup"><span data-stu-id="4de18-199">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="4de18-200">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="4de18-200">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="4de18-201">要求篩選</span><span class="sxs-lookup"><span data-stu-id="4de18-201">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-202">Windows Server 功能</span><span class="sxs-lookup"><span data-stu-id="4de18-202">Windows Server Features</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="4de18-203">.NET Framework 4.5 功能：</span><span class="sxs-lookup"><span data-stu-id="4de18-203">.NET Framework 4.5 features:</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="4de18-204">.NET Framework 4.5 或4。6</span><span class="sxs-lookup"><span data-stu-id="4de18-204">.NET Framework 4.5 or 4.6</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="4de18-205">Windows Server 2016 </strong> - .net Framework 4.6 已安裝在這些版本的 Windows Server 上，但您必須啟用它。</span><span class="sxs-lookup"><span data-stu-id="4de18-205">Windows Server 2016</strong> - .NET Framework 4.6 is already installed for these versions of Windows Server, but you must enable it.</span></span></p></li>  
<li><p><strong><span data-ttu-id="4de18-206">Windows server 2012 或 Windows Server 2012 R2 </strong> - .net Framework 4.5 已針對這些版本的 Windows Server 安裝，但您必須啟用它。</span><span class="sxs-lookup"><span data-stu-id="4de18-206">Windows Server 2012 or Windows Server 2012 R2</strong> - .NET Framework 4.5 is already installed for these versions of Windows Server, but you must enable it.</span></span></p></li>
<li><p><strong><span data-ttu-id="4de18-207">Windows server </strong> - 2008 r2 不隨附 windows Server 2008 R2 .net framework 4.5，因此您必須 <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)"> 下載 Microsoft .net framework 4.5 </a> 並另行安裝。</span><span class="sxs-lookup"><span data-stu-id="4de18-207">Windows Server 2008 R2</strong> - .NET Framework 4.5 is not included with Windows Server 2008 R2, so you must <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)">download Microsoft .NET Framework 4.5</a> and install it separately.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4de18-208">注意</span><span class="sxs-lookup"><span data-stu-id="4de18-208">Note</span></span></strong><br/><p><span data-ttu-id="4de18-209">如果您是從 MBAM 2.0 或 MBAM 2.0 SP1 升級，且需要安裝 .NET Framework 4.5，請參閱 MBAM 2.5 的版本資訊，以 <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"> </a> 取得讓網站正常運作的其他必要步驟。</span><span class="sxs-lookup"><span data-stu-id="4de18-209">If you are upgrading from MBAM 2.0 or MBAM 2.0 SP1 and need to install .NET Framework 4.5, see <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)">Release Notes for MBAM 2.5</a> for an additional required step to make the websites work.</span></span></p>
</div>
<div>

</div></li>
</ul></li>
<li><p><strong><span data-ttu-id="4de18-210">WCF 啟用</span><span class="sxs-lookup"><span data-stu-id="4de18-210">WCF Activation</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="4de18-211">HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="4de18-211">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="4de18-212">非 HTTP 啟用（僅適用于 Windows Server 2008、2012和 2012 R2）</span><span class="sxs-lookup"><span data-stu-id="4de18-212">Non-HTTP Activation (Only for Windows Server 2008, 2012, and 2012 R2)</span></span></p>
<p></p></li>
</ul></li>
<li><p><strong><span data-ttu-id="4de18-213">TCP 啟用</span><span class="sxs-lookup"><span data-stu-id="4de18-213">TCP Activation</span></span></strong></p></li>
</ul>
<p><strong><span data-ttu-id="4de18-214">Windows Process Activation Service：</span><span class="sxs-lookup"><span data-stu-id="4de18-214">Windows Process Activation Service:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="4de18-215">處理模型</span><span class="sxs-lookup"><span data-stu-id="4de18-215">Process Model</span></span></p></li>
<li><p><span data-ttu-id="4de18-216">.NET Framework 環境</span><span class="sxs-lookup"><span data-stu-id="4de18-216">.NET Framework Environment</span></span></p></li>
<li><p><span data-ttu-id="4de18-217">配置 Api</span><span class="sxs-lookup"><span data-stu-id="4de18-217">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-218">ASP.NET MVC 4。0</span><span class="sxs-lookup"><span data-stu-id="4de18-218">ASP.NET MVC 4.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)"><span data-ttu-id="4de18-219">ASP.NET MVC 4 下載</span><span class="sxs-lookup"><span data-stu-id="4de18-219">ASP.NET MVC 4 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-220">服務主體名稱（SPN）</span><span class="sxs-lookup"><span data-stu-id="4de18-220">Service Principal Name (SPN)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-221">Web 應用程式需要在您用於 web 應用程式池之網域帳戶下的虛擬主機名稱稱中使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="4de18-221">The web applications require an SPN for the virtual host name under the domain account that you use for the web application pools.</span></span></p>
<p><span data-ttu-id="4de18-222">如果您的系統管理許可權允許您在 Active Directory 網域服務中建立 Spn，MBAM 會為您建立 SPN。</span><span class="sxs-lookup"><span data-stu-id="4de18-222">If your administrative rights permit you to create SPNs in Active Directory Domain Services, MBAM creates the SPN for you.</span></span> <span data-ttu-id="4de18-223">請參閱 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> Setspn </a> ，以取得建立 spn 所需許可權的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4de18-223">See <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Setspn</a> for information about the rights required to create SPNs.</span></span></p>
<p><span data-ttu-id="4de18-224">如果您沒有建立 Spn 的系統管理許可權，您必須使用下列命令要求貴組織中的 Active Directory 系統管理員為您建立 SPN。</span><span class="sxs-lookup"><span data-stu-id="4de18-224">If you do not have administrative rights to create SPNs, you must ask the Active Directory administrators in your organization to create the SPN for you by using the following command.</span></span></p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p><span data-ttu-id="4de18-225">在程式碼範例中，虛擬主機名稱是 mbamvirtual.contoso.com，而用於 web 應用程式池的網域帳戶是 contoso\mbamapppooluser。</span><span class="sxs-lookup"><span data-stu-id="4de18-225">In the code example, the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\mbamapppooluser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4de18-226">注意</span><span class="sxs-lookup"><span data-stu-id="4de18-226">Note</span></span></strong><br/><p><span data-ttu-id="4de18-227">如果您要設定負載平衡，請在所有伺服器上使用相同的應用程式池帳戶。</span><span class="sxs-lookup"><span data-stu-id="4de18-227">If you are setting up Load Balancing, use the same application pool account on all servers.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="4de18-228">如需針對完整、NetBIOS 及自訂主機名稱登記 Spn 的詳細資訊，請參閱 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 規劃如何保護 MBAM 網站 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4de18-228">For more information about registering SPNs for fully qualified, NetBIOS, and custom host names, see <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)">Planning How to Secure the MBAM Websites</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4de18-229">自助服務入口網站的先決條件</span><span class="sxs-lookup"><span data-stu-id="4de18-229">Prerequisites for the Self-Service Portal</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-230">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-230">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-231">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-231">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-232">支援的 Windows Server 版本</span><span class="sxs-lookup"><span data-stu-id="4de18-232">Supported version of Windows Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-233"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="4de18-233">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-234">ASP.NET MVC 4。0</span><span class="sxs-lookup"><span data-stu-id="4de18-234">ASP.NET MVC 4.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)"><span data-ttu-id="4de18-235">ASP.NET MVC 4 下載</span><span class="sxs-lookup"><span data-stu-id="4de18-235">ASP.NET MVC 4 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-236">Web 服務 IIS 管理工具</span><span class="sxs-lookup"><span data-stu-id="4de18-236">Web Service IIS Management Tools</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-237">服務主體名稱（SPN）</span><span class="sxs-lookup"><span data-stu-id="4de18-237">Service Principal Name (SPN)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-238">Web 應用程式需要在您用於 web 應用程式池之網域帳戶下的虛擬主機名稱稱中使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="4de18-238">The web applications require an SPN for the virtual host name under the domain account that you use for the web application pools.</span></span></p>
<p><span data-ttu-id="4de18-239">如果您的系統管理許可權允許您在 Active Directory 網域服務中建立 Spn，MBAM 會為您建立 SPN。</span><span class="sxs-lookup"><span data-stu-id="4de18-239">If your administrative rights permit you to create SPNs in Active Directory Domain Services, MBAM creates the SPN for you.</span></span> <span data-ttu-id="4de18-240">請參閱 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> Setspn </a> ，以取得建立 spn 所需許可權的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4de18-240">See <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Setspn</a> for information about the rights required to create SPNs.</span></span></p>
<p><span data-ttu-id="4de18-241">如果您沒有建立 Spn 的系統管理許可權，您必須使用下列命令，要求貴組織中組織管理員的 Active Directory 系統管理員為您建立 SPN。</span><span class="sxs-lookup"><span data-stu-id="4de18-241">If you do not have administrative rights to create SPNs, you must ask the Active Directory administrators in your organization administrators in your organization to create the SPN for you by using the following command.</span></span></p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p><span data-ttu-id="4de18-242">在程式碼範例中，虛擬主機名稱是 mbamvirtual.contoso.com，而用於 web 應用程式池的網域帳戶是 contoso\mbamapppooluser。</span><span class="sxs-lookup"><span data-stu-id="4de18-242">In the code example, the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\mbamapppooluser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4de18-243">注意</span><span class="sxs-lookup"><span data-stu-id="4de18-243">Note</span></span></strong><br/><p><span data-ttu-id="4de18-244">如果您要設定負載平衡，請在所有伺服器上使用相同的應用程式池帳戶。</span><span class="sxs-lookup"><span data-stu-id="4de18-244">If you are setting up Load Balancing, use the same application pool account on all servers.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="4de18-245">如需針對完整、NetBIOS 及自訂主機名稱登記 Spn 的詳細資訊，請參閱 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 規劃如何保護 MBAM 網站 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4de18-245">For more information about registering SPNs for fully qualified, NetBIOS, and custom host names, see <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)">Planning How to Secure the MBAM Websites</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4de18-246">管理工作站的先決條件</span><span class="sxs-lookup"><span data-stu-id="4de18-246">Prerequisites for the Management Workstation</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-247">必備</span><span class="sxs-lookup"><span data-stu-id="4de18-247">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4de18-248">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4de18-248">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-249">在安裝 MBAM 用戶端之前，請先從 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何取得 MDOP 群組原則（admx）範本中下載 MBAM 群組原則範本 </a> ，並使用您要在企業中實現的設定（在您的 BitLocker 磁片磁碟機加密中）來設定它們。</span><span class="sxs-lookup"><span data-stu-id="4de18-249">Before installing the MBAM Client, download the MBAM Group Policy Templates from <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">How to Get MDOP Group Policy (.admx) Templates</a> and configure them with the settings that you want to implement in your enterprise for BitLocker Drive Encryption.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4de18-250">在安裝 MBAM 用戶端之前，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4de18-250">Before installing the MBAM Client, do the following:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4de18-251">工作</span><span class="sxs-lookup"><span data-stu-id="4de18-251">What to do</span></span></th>
<th align="left"><span data-ttu-id="4de18-252">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="4de18-252">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4de18-253">複製 MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="4de18-253">Copy the MBAM Group Policy Templates</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="4de18-254">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="4de18-254">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4de18-255">編輯群組原則設定</span><span class="sxs-lookup"><span data-stu-id="4de18-255">Edit the Group Policy settings</span></span></p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"><span data-ttu-id="4de18-256">編輯 MBAM 2.5 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="4de18-256">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>





## <span data-ttu-id="4de18-257">相關主題</span><span class="sxs-lookup"><span data-stu-id="4de18-257">Related topics</span></span>


[<span data-ttu-id="4de18-258">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="4de18-258">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="4de18-259">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="4de18-259">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="4de18-260">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="4de18-260">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)




## <span data-ttu-id="4de18-261">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="4de18-261">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4de18-262">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="4de18-262">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="4de18-263">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4de18-263">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




