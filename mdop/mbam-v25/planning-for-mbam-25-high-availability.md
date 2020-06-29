---
title: MBAM 2.5 高可用性規劃
description: MBAM 2.5 高可用性規劃
author: dansimp
ms.assetid: 1e29b30c-33f1-4a52-9442-8c1391f0049c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 20c304f669cfe9e1484be47dea1b9fcc917aea2c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812057"
---
# <span data-ttu-id="7f278-103">MBAM 2.5 高可用性規劃</span><span class="sxs-lookup"><span data-stu-id="7f278-103">Planning for MBAM 2.5 High Availability</span></span>


<span data-ttu-id="7f278-104">Microsoft BitLocker 管理與監控（MBAM）可透過使用下列一或多項技術來維持高可用性，如下節所述：</span><span class="sxs-lookup"><span data-stu-id="7f278-104">Microsoft BitLocker Administration and Monitoring (MBAM) can maintain high availability through use of one or more of the following technologies, which are described in the following sections:</span></span>

-   [<span data-ttu-id="7f278-105">SQL Server AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="7f278-105">SQL Server AlwaysOn availability groups</span></span>](#bkmk-alwayson)

-   [<span data-ttu-id="7f278-106">Microsoft SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="7f278-106">Microsoft SQL Server clustering</span></span>](#bkmk-sql-clustering)

-   [<span data-ttu-id="7f278-107">IIS 網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="7f278-107">IIS Network Load Balancing</span></span>](#bkmk-load-balance)

-   [<span data-ttu-id="7f278-108">SQL Server 中的資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="7f278-108">Database mirroring in SQL Server</span></span>](#bkmk-db-mirroring)

-   [<span data-ttu-id="7f278-109">使用 [卷影複製服務（VSS）] 備份 MBAM 資料庫</span><span class="sxs-lookup"><span data-stu-id="7f278-109">Backing up MBAM databases by using the Volume Shadow Copy Service (VSS)</span></span>](#bkmk-vss)

<span data-ttu-id="7f278-110">使用下列各節中的資訊，協助您瞭解以高可用性配置來部署 MBAM 的選項。</span><span class="sxs-lookup"><span data-stu-id="7f278-110">Use the information in the following sections to help you understand the options to deploy MBAM in a highly available configuration.</span></span>

## <a href="" id="bkmk-alwayson"></a><span data-ttu-id="7f278-111">SQL Server AlwaysOn 可用性群組的支援</span><span class="sxs-lookup"><span data-stu-id="7f278-111">Support for SQL Server AlwaysOn availability groups</span></span>


<span data-ttu-id="7f278-112">MBAM 可讓您設定及管理 Microsoft SQL Server 中的資料庫可用性群組。</span><span class="sxs-lookup"><span data-stu-id="7f278-112">MBAM enables you to configure and manage availability groups for the databases in Microsoft SQL Server.</span></span> <span data-ttu-id="7f278-113">MBAM 的可用性群組支援容錯移轉環境，在此情況下，合規性和審核資料庫及復原資料庫會一起進行容錯移轉，而不是單獨進行。</span><span class="sxs-lookup"><span data-stu-id="7f278-113">An availability group for MBAM supports a failover environment where the Compliance and Audit Database and the Recovery Database fail over together rather than separately.</span></span>

<span data-ttu-id="7f278-114">可用性群組支援一組可讀/寫的主資料庫，以及一到四組對應的次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="7f278-114">An availability group supports a set of read/write primary databases and one to four sets of corresponding secondary databases.</span></span> <span data-ttu-id="7f278-115">或者，您也可以將次要資料庫提供給唯讀許可權、部份備份作業，或同時適用于這兩者。</span><span class="sxs-lookup"><span data-stu-id="7f278-115">Optionally, secondary databases can be made available for read-only permission, some backup operations, or for both.</span></span>

<span data-ttu-id="7f278-116">如需有關如何設定可用性群組的詳細資訊，請參閱[AlwaysOn 可用性群組](https://go.microsoft.com/fwlink/?LinkId=393277)。</span><span class="sxs-lookup"><span data-stu-id="7f278-116">For information about how to set up availability groups, see [AlwaysOn Availability Groups](https://go.microsoft.com/fwlink/?LinkId=393277).</span></span>

## <a href="" id="bkmk-sql-clustering"></a><span data-ttu-id="7f278-117">Microsoft SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="7f278-117">Microsoft SQL Server clustering</span></span>


<span data-ttu-id="7f278-118">您可以在執行 SQL Server 群集的電腦上執行 MBAM 2.5 合規性和審核資料庫及復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="7f278-118">You can run the MBAM 2.5 Compliance and Audit Database and the Recovery Database on computers that are running SQL Server clusters.</span></span>

## <a href="" id="bkmk-load-balance"></a><span data-ttu-id="7f278-119">IIS 網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="7f278-119">IIS Network Load Balancing</span></span>


<span data-ttu-id="7f278-120">您可以使用網路負載平衡來針對執行管理和監控網站（也稱為說明服務台）、自助入口網站和 web 服務（透過網際網路資訊服務（IIS）部署的電腦）來設定高可用性環境。</span><span class="sxs-lookup"><span data-stu-id="7f278-120">You can use Network Load Balancing to configure a highly available environment for computers that are running the Administration and Monitoring Website (also known as Help Desk), the Self-Service Portal, and the web services, which are deployed through Internet Information Services (IIS).</span></span>

### <span data-ttu-id="7f278-121">必要條件</span><span class="sxs-lookup"><span data-stu-id="7f278-121">Prerequisites</span></span>

<span data-ttu-id="7f278-122">在設定負載平衡前，請確定您已符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="7f278-122">Before configuring load balancing, ensure that you have met the following prerequisites:</span></span>

-   <span data-ttu-id="7f278-123">必須提供負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="7f278-123">A load balancer must be available.</span></span> <span data-ttu-id="7f278-124">您可以使用來自 Microsoft 或其他公司的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="7f278-124">You can use load balancers from Microsoft or another company.</span></span> <span data-ttu-id="7f278-125">如需 Microsoft 負載平衡器技術的詳細資訊，請參閱[使用 IIS 伺服器建立網頁群](https://go.microsoft.com/fwlink/?LinkId=393326)。</span><span class="sxs-lookup"><span data-stu-id="7f278-125">For more information about Microsoft load balancer technology, see [Build a Web Farm with IIS Servers](https://go.microsoft.com/fwlink/?LinkId=393326).</span></span>

-   <span data-ttu-id="7f278-126">至少有兩個伺服器正在執行 IIS，且已滿足所有 MBAM 先決條件以支援其網頁功能，包括 ASP.NET MVC 4。</span><span class="sxs-lookup"><span data-stu-id="7f278-126">At least two servers are running IIS and have met all of the MBAM prerequisites to support its web features, including ASP.NET MVC 4.</span></span>

-   <span data-ttu-id="7f278-127">MBAM 資料庫和報表是在伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="7f278-127">MBAM databases and reports are running on a server.</span></span>

### <a href="" id="-------------mbam-specific-changes-that-are-required-to-enable-load-balancing"></a> <span data-ttu-id="7f278-128">啟用負載平衡所需的 MBAM 特定變更</span><span class="sxs-lookup"><span data-stu-id="7f278-128">MBAM-specific changes that are required to enable Load Balancing</span></span>

<span data-ttu-id="7f278-129">完成下列任務：</span><span class="sxs-lookup"><span data-stu-id="7f278-129">Complete the following tasks:</span></span>

1.  <span data-ttu-id="7f278-130">在您用於 web 應用程式池之網域帳戶底下的虛擬主機名稱稱上，註冊服務主體名稱（SPN）。</span><span class="sxs-lookup"><span data-stu-id="7f278-130">Register a Service Principal Name (SPN) for the virtual host name under the domain account that you are using for the web application pools.</span></span> <span data-ttu-id="7f278-131">例如，如果虛擬主機名稱是 mbamvirtual.contoso.com，而用於 web 應用程式池的網域帳戶是 contoso\\mbamapppooluser，則下列命令會適當地註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="7f278-131">For example, if the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\\mbamapppooluser, the following command registers the SPN appropriately.</span></span>

    `Setspn -s http//mbamvirtual contoso\mbamapppooluser`

    `Setspn -s http//mbamvirtual.contoso.com contoso\mbamapppooluser`

2.  <span data-ttu-id="7f278-132">設定下列 MBAM 網頁功能：</span><span class="sxs-lookup"><span data-stu-id="7f278-132">Configure the following MBAM web features:</span></span>

    -   <span data-ttu-id="7f278-133">在將承載 MBAM 網頁功能的每個伺服器上，針對應用程式池管理認證使用相同的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f278-133">On each server that will host the MBAM web features, use the same domain account for the application pool administrative credentials.</span></span>

    -   <span data-ttu-id="7f278-134">指定與負載平衡群集的虛擬主機名稱（DNS 名稱）相符的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="7f278-134">Specify a host name that matches the virtual host name (DNS name) of the Load Balancing cluster.</span></span> <span data-ttu-id="7f278-135">例如，當您在名為「NLB1」的伺服器上安裝 MBAM 的虛擬主機名稱為**mbamvirtual.contoso.com**時，請確定您在 Windows PowerShell Cmdlet 中指定的主機名稱是**mbamvirtual.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="7f278-135">For example, when you install MBAM on a server called "NLB1" with a virtual host name of **mbamvirtual.contoso.com**, ensure that the host name that you specify in the Windows PowerShell cmdlet is **mbamvirtual.contoso.com**.</span></span>

3.  <span data-ttu-id="7f278-136">如果您是使用負載平衡器在網頁群中設定網站，您必須將網站設定為使用相同的電腦金鑰。</span><span class="sxs-lookup"><span data-stu-id="7f278-136">If you are configuring the websites in a web farm with a load balancer, you must configure the websites to use the same machine key.</span></span>

    <span data-ttu-id="7f278-137">如需詳細資訊，請參閱[MachineKey 元素（ASP.NET 設定架構）](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx)中的下列各節：</span><span class="sxs-lookup"><span data-stu-id="7f278-137">For more information, see the following sections in [machineKey Element (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx):</span></span>

    -   <span data-ttu-id="7f278-138">機器金鑰說明</span><span class="sxs-lookup"><span data-stu-id="7f278-138">Machine Key Explained</span></span>

    -   <span data-ttu-id="7f278-139">網頁伺服器陣列的部署考慮</span><span class="sxs-lookup"><span data-stu-id="7f278-139">Web Farm Deployment Considerations</span></span>

    <span data-ttu-id="7f278-140">如需如何自動產生金鑰的指示，請參閱[產生電腦金鑰（IIS 7）](https://technet.microsoft.com/library/cc772287.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7f278-140">For instructions about how to automatically generate a key, see [Generate a Machine Key (IIS 7)](https://technet.microsoft.com/library/cc772287.aspx).</span></span>

<span data-ttu-id="7f278-141">有關負載平衡的資訊也適用于 Windows Server 2012 或 Windows Server2008R2 中的 IIS 網路負載平衡（NLB）群集。</span><span class="sxs-lookup"><span data-stu-id="7f278-141">The information about Load Balancing also applies to IIS Network Load Balancing (NLB) clusters in Windows Server 2012 or Windows Server2008R2.</span></span> <span data-ttu-id="7f278-142">Windows Server 2012 中的 IIS 網路負載平衡功能通常與在 Windows Server2008R2 中一樣。</span><span class="sxs-lookup"><span data-stu-id="7f278-142">The IIS Network Load Balancing functionality in Windows Server 2012 is generally the same as in Windows Server2008R2.</span></span> <span data-ttu-id="7f278-143">不過，某些工作的詳細資料在 Windows Server 2012 中是不一樣的。</span><span class="sxs-lookup"><span data-stu-id="7f278-143">However, some task details are different in Windows Server 2012.</span></span> <span data-ttu-id="7f278-144">如需執行工作的新方法的相關資訊，請參閱[Windows Server 2012 R2 Preview 和 Windows server 2012 中的常見管理工作與流覽](https://go.microsoft.com/fwlink/?LinkId=316371)。</span><span class="sxs-lookup"><span data-stu-id="7f278-144">For information about new ways to do tasks, see [Common Management Tasks and Navigation in Windows Server 2012 R2 Preview and Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316371).</span></span>

## <a href="" id="bkmk-db-mirroring"></a><span data-ttu-id="7f278-145">SQL Server 中的資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="7f278-145">Database mirroring in SQL Server</span></span>


<span data-ttu-id="7f278-146">MBAM 支援使用 SQL Server 鏡像，在這種情況下，您可以使用兩個 SQL Server 實例（針對每個資料庫）來鏡像合規性和審核資料庫及復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="7f278-146">MBAM supports the use of SQL Server mirroring, where the Compliance and Audit Database and the Recovery Database are mirrored by using two instances of SQL Server for each database.</span></span> <span data-ttu-id="7f278-147">在實施鏡像之前，請注意，鏡像會慢慢地逐步推出，以適應本主題中前面所述的可用性群組。</span><span class="sxs-lookup"><span data-stu-id="7f278-147">Before implementing mirroring, be aware that mirroring is slowly being phased out, in favor of availability groups, which are discussed earlier in this topic.</span></span>

<span data-ttu-id="7f278-148">若要實現 MBAM 的鏡像，您必須使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet，為鏡像資料庫設定指定適當的連接字串。</span><span class="sxs-lookup"><span data-stu-id="7f278-148">To implement mirroring for MBAM, you must specify the appropriate connection strings for the mirrored database configuration by using the **Enable-MbamWebApplication** Windows PowerShell cmdlet.</span></span> <span data-ttu-id="7f278-149">如需有關 MBAM 2.5 Windows PowerShell Cmdlet 的詳細資訊，請參閱[使用 Windows powershell 來設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7f278-149">For more information about the MBAM 2.5 Windows PowerShell cmdlets, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

### <span data-ttu-id="7f278-150">使用 Windows PowerShell 實現 SQL Server 鏡像的範例</span><span class="sxs-lookup"><span data-stu-id="7f278-150">Examples of implementing SQL Server mirroring by using Windows PowerShell</span></span>

<span data-ttu-id="7f278-151">下列範例示範如何使用 Windows PowerShell Cmdlet 來實現 SQL Server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="7f278-151">The following examples show how you might implement SQL Server mirroring by using Windows PowerShell cmdlets.</span></span>

**<span data-ttu-id="7f278-152">範例 1</span><span class="sxs-lookup"><span data-stu-id="7f278-152">Example 1</span></span>**

``` syntax
Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -AdvancedHelpdeskAccessGroup “MyDomain\AdvancedUserGroup” -HelpdeskAccessGroup “MyDomain\StandardUserGroup” -ReportsReadOnlyAccessGroup "MyDomain\ReportUserGroup" -ReportUrl "https://MyReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

**<span data-ttu-id="7f278-153">範例 2</span><span class="sxs-lookup"><span data-stu-id="7f278-153">Example 2</span></span>**

``` syntax
Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer; Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;I Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

### <span data-ttu-id="7f278-154">有關 SQL Server 鏡像的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7f278-154">More information about SQL Server mirroring</span></span>

<span data-ttu-id="7f278-155">下列連結提供更多關於設定 SQL Server 鏡像的資訊：</span><span class="sxs-lookup"><span data-stu-id="7f278-155">The following links provide more information about configuring SQL Server mirroring:</span></span>

-   [<span data-ttu-id="7f278-156">操作方法：準備鏡像資料庫以進行鏡像（Transact-sql）</span><span class="sxs-lookup"><span data-stu-id="7f278-156">How to: Prepare a Mirror Database for Mirroring (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=316375)

-   [<span data-ttu-id="7f278-157">使用 Windows 驗證建立資料庫鏡像會話（SQL Server Management Studio）</span><span class="sxs-lookup"><span data-stu-id="7f278-157">Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)</span></span>](https://go.microsoft.com/fwlink/?LinkId=316377)

## <a href="" id="bkmk-vss"></a><span data-ttu-id="7f278-158">使用 [卷影複製服務（VSS）] 備份 MBAM 資料庫</span><span class="sxs-lookup"><span data-stu-id="7f278-158">Backing up MBAM databases by using the Volume Shadow Copy Service (VSS)</span></span>


<span data-ttu-id="7f278-159">MBAM 提供了 Volume Shadow Copy 服務（VSS）寫入程式，稱為 Microsoft BitLocker 管理與管理寫入程式。</span><span class="sxs-lookup"><span data-stu-id="7f278-159">MBAM provides a Volume Shadow Copy Service (VSS) writer, called the Microsoft BitLocker Administration and Management Writer.</span></span> <span data-ttu-id="7f278-160">這個 VSS 寫入程式方便了合規性和審核資料庫及復原資料庫的備份。</span><span class="sxs-lookup"><span data-stu-id="7f278-160">This VSS writer facilitates the backup of the Compliance and Audit Database and the Recovery Database.</span></span>

<span data-ttu-id="7f278-161">VSS 書寫器會在您啟用 MBAM web 應用程式的每個伺服器上註冊。</span><span class="sxs-lookup"><span data-stu-id="7f278-161">The VSS writer is registered on every server where you enable an MBAM web application.</span></span> <span data-ttu-id="7f278-162">MBAM VSS 書寫器取決於 SQL Server VSS 書寫器，該書寫器已註冊為 Microsoft SQL Server 安裝的一部分。</span><span class="sxs-lookup"><span data-stu-id="7f278-162">The MBAM VSS writer depends on the SQL Server VSS Writer, which is registered as part of the Microsoft SQL Server installation.</span></span> <span data-ttu-id="7f278-163">任何使用 VSS 寫入程式來執行備份的備份技術，都可以探索 MBAM VSS 寫入程式。</span><span class="sxs-lookup"><span data-stu-id="7f278-163">Any backup technology that uses VSS writers to perform backup can discover the MBAM VSS writer.</span></span>



## <span data-ttu-id="7f278-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f278-164">Related topics</span></span>


[<span data-ttu-id="7f278-165">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="7f278-165">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 

 
## <span data-ttu-id="7f278-166">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="7f278-166">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="7f278-167">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="7f278-167">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="7f278-168">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="7f278-168">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




