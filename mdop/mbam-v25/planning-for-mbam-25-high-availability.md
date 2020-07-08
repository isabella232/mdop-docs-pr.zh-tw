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
# MBAM 2.5 高可用性規劃


Microsoft BitLocker 管理與監控（MBAM）可透過使用下列一或多項技術來維持高可用性，如下節所述：

-   [SQL Server AlwaysOn 可用性群組](#bkmk-alwayson)

-   [Microsoft SQL Server 群集](#bkmk-sql-clustering)

-   [IIS 網路負載平衡](#bkmk-load-balance)

-   [SQL Server 中的資料庫鏡像](#bkmk-db-mirroring)

-   [使用 [卷影複製服務（VSS）] 備份 MBAM 資料庫](#bkmk-vss)

使用下列各節中的資訊，協助您瞭解以高可用性配置來部署 MBAM 的選項。

## <a href="" id="bkmk-alwayson"></a>SQL Server AlwaysOn 可用性群組的支援


MBAM 可讓您設定及管理 Microsoft SQL Server 中的資料庫可用性群組。 MBAM 的可用性群組支援容錯移轉環境，在此情況下，合規性和審核資料庫及復原資料庫會一起進行容錯移轉，而不是單獨進行。

可用性群組支援一組可讀/寫的主資料庫，以及一到四組對應的次要資料庫。 或者，您也可以將次要資料庫提供給唯讀許可權、部份備份作業，或同時適用于這兩者。

如需有關如何設定可用性群組的詳細資訊，請參閱[AlwaysOn 可用性群組](https://go.microsoft.com/fwlink/?LinkId=393277)。

## <a href="" id="bkmk-sql-clustering"></a>Microsoft SQL Server 群集


您可以在執行 SQL Server 群集的電腦上執行 MBAM 2.5 合規性和審核資料庫及復原資料庫。

## <a href="" id="bkmk-load-balance"></a>IIS 網路負載平衡


您可以使用網路負載平衡來針對執行管理和監控網站（也稱為說明服務台）、自助入口網站和 web 服務（透過網際網路資訊服務（IIS）部署的電腦）來設定高可用性環境。

### 必要條件

在設定負載平衡前，請確定您已符合下列先決條件：

-   必須提供負載平衡器。 您可以使用來自 Microsoft 或其他公司的負載平衡器。 如需 Microsoft 負載平衡器技術的詳細資訊，請參閱[使用 IIS 伺服器建立網頁群](https://go.microsoft.com/fwlink/?LinkId=393326)。

-   至少有兩個伺服器正在執行 IIS，且已滿足所有 MBAM 先決條件以支援其網頁功能，包括 ASP.NET MVC 4。

-   MBAM 資料庫和報表是在伺服器上執行。

### <a href="" id="-------------mbam-specific-changes-that-are-required-to-enable-load-balancing"></a> 啟用負載平衡所需的 MBAM 特定變更

完成下列任務：

1.  在您用於 web 應用程式池之網域帳戶底下的虛擬主機名稱稱上，註冊服務主體名稱（SPN）。 例如，如果虛擬主機名稱是 mbamvirtual.contoso.com，而用於 web 應用程式池的網域帳戶是 contoso\\mbamapppooluser，則下列命令會適當地註冊 SPN。

    `Setspn -s http//mbamvirtual contoso\mbamapppooluser`

    `Setspn -s http//mbamvirtual.contoso.com contoso\mbamapppooluser`

2.  設定下列 MBAM 網頁功能：

    -   在將承載 MBAM 網頁功能的每個伺服器上，針對應用程式池管理認證使用相同的網域帳戶。

    -   指定與負載平衡群集的虛擬主機名稱（DNS 名稱）相符的主機名稱。 例如，當您在名為「NLB1」的伺服器上安裝 MBAM 的虛擬主機名稱為**mbamvirtual.contoso.com**時，請確定您在 Windows PowerShell Cmdlet 中指定的主機名稱是**mbamvirtual.contoso.com**。

3.  如果您是使用負載平衡器在網頁群中設定網站，您必須將網站設定為使用相同的電腦金鑰。

    如需詳細資訊，請參閱[MachineKey 元素（ASP.NET 設定架構）](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx)中的下列各節：

    -   機器金鑰說明

    -   網頁伺服器陣列的部署考慮

    如需如何自動產生金鑰的指示，請參閱[產生電腦金鑰（IIS 7）](https://technet.microsoft.com/library/cc772287.aspx)。

有關負載平衡的資訊也適用于 Windows Server 2012 或 Windows Server2008R2 中的 IIS 網路負載平衡（NLB）群集。 Windows Server 2012 中的 IIS 網路負載平衡功能通常與在 Windows Server2008R2 中一樣。 不過，某些工作的詳細資料在 Windows Server 2012 中是不一樣的。 如需執行工作的新方法的相關資訊，請參閱[Windows Server 2012 R2 Preview 和 Windows server 2012 中的常見管理工作與流覽](https://go.microsoft.com/fwlink/?LinkId=316371)。

## <a href="" id="bkmk-db-mirroring"></a>SQL Server 中的資料庫鏡像


MBAM 支援使用 SQL Server 鏡像，在這種情況下，您可以使用兩個 SQL Server 實例（針對每個資料庫）來鏡像合規性和審核資料庫及復原資料庫。 在實施鏡像之前，請注意，鏡像會慢慢地逐步推出，以適應本主題中前面所述的可用性群組。

若要實現 MBAM 的鏡像，您必須使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet，為鏡像資料庫設定指定適當的連接字串。 如需有關 MBAM 2.5 Windows PowerShell Cmdlet 的詳細資訊，請參閱[使用 Windows powershell 來設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。

### 使用 Windows PowerShell 實現 SQL Server 鏡像的範例

下列範例示範如何使用 Windows PowerShell Cmdlet 來實現 SQL Server 鏡像。

**範例 1**

``` syntax
Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -AdvancedHelpdeskAccessGroup “MyDomain\AdvancedUserGroup” -HelpdeskAccessGroup “MyDomain\StandardUserGroup” -ReportsReadOnlyAccessGroup "MyDomain\ReportUserGroup" -ReportUrl "https://MyReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

**範例 2**

``` syntax
Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer; Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;I Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

### 有關 SQL Server 鏡像的詳細資訊

下列連結提供更多關於設定 SQL Server 鏡像的資訊：

-   [操作方法：準備鏡像資料庫以進行鏡像（Transact-sql）](https://go.microsoft.com/fwlink/?LinkId=316375)

-   [使用 Windows 驗證建立資料庫鏡像會話（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=316377)

## <a href="" id="bkmk-vss"></a>使用 [卷影複製服務（VSS）] 備份 MBAM 資料庫


MBAM 提供了 Volume Shadow Copy 服務（VSS）寫入程式，稱為 Microsoft BitLocker 管理與管理寫入程式。 這個 VSS 寫入程式方便了合規性和審核資料庫及復原資料庫的備份。

VSS 書寫器會在您啟用 MBAM web 應用程式的每個伺服器上註冊。 MBAM VSS 書寫器取決於 SQL Server VSS 書寫器，該書寫器已註冊為 Microsoft SQL Server 安裝的一部分。 任何使用 VSS 寫入程式來執行備份的備份技術，都可以探索 MBAM VSS 寫入程式。



## 相關主題


[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




