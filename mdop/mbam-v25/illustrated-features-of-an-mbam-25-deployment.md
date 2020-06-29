---
title: MBAM 2.5 部署的功能圖例
description: MBAM 2.5 部署的功能圖例
author: dansimp
ms.assetid: 7b5eff42-af8c-4bd0-a20a-18cc2e779f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: c3b205d4f0b4b18cf8bdbf51982b5a59e5e1b9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800083"
---
# MBAM 2.5 部署的功能圖例


本主題描述針對下列拓撲進行 Microsoft BitLocker 管理和監控（MBAM）2.5 部署的個別功能：

-   獨立 MBAM

-   System Center Configuration Manager 整合

**重要**  
這些功能不代表部署 MBAM 的建議結構。 此資訊只能用來瞭解組成 MBAM 部署的個別功能。 請參閱適用于[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)，以取得 MBAM 的建議架構。



如需本主題中所述軟體支援版本的清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。

## <a href="" id="bkmk-standalone"></a> MBAM 獨立拓朴


下列影像和表格說明 MBAM 獨立拓撲中的功能。

![mbab2\-5](images/mbam2-5-standalonecomponents.png)

|功能類型|描述|資料庫|
|-|-|-|
|復原資料庫|此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。|此功能是在執行 Windows Server 的伺服器以及支援的 SQL Server 實例上設定。|
|合規性和審核資料庫|此資料庫儲存合規性資料，主要用於 SQL Server Reporting Services 主機的報表。|此功能是在執行 Windows Server 的伺服器以及支援的 SQL Server 實例上設定。|
|合規性與審計報告|||
|報告 Web 服務|此 web 服務可讓您在管理與監控網站以及儲存報告資料的 SQL Server 實例之間進行通訊。|此功能已安裝在執行 Windows Server 的伺服器上。|
|報告網站（管理和監控網站）|您可以從 [管理和監控] 網站查看報告。 報告會提供企業中用戶端電腦的復原審核及合規性狀態資料。|此功能是在執行 Windows Server 的伺服器上設定。|
|SQL Server Reporting Services （SSRS）|報告是在 SSRS 資料庫實例中設定。 報告可以直接從 SSRS 查看，或從管理和監控網站查看。|此功能是在執行 Windows Server 的伺服器以及執行 SSRS 的支援的 SQL Server 實例上設定。|
|自助服務伺服器|||
|自助服務 Web 服務|此 web 服務是由 MBAM 用戶端和 [管理及監視] 網站和自助服務入口網站使用，以與恢復資料庫進行通訊。|此功能已安裝在執行 Windows Server 的電腦上。|
|自助式網站（自助服務入口網站）|此網站可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。|此功能是在執行 Windows Server 的電腦上設定。|
|管理和監控伺服器|||
|管理和監控 Web 服務|MBAM 用戶端和網站會使用監視 Web 服務來與資料庫進行通訊。|此功能已安裝在執行 Windows Server 的電腦上。|

**重要**  
在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供自助服務 Web 服務，其中的 MBAM 用戶端、管理和監控網站，以及自助式入口網站直接與恢復資料庫進行通訊。

**重要**  
因為 MBAM 用戶端和網站直接與復原資料庫通訊，所以在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中已不再提供監視 Web 服務。


## <a href="" id="bkmk-cmintegrated"></a>System Center Configuration Manager 整合拓撲

下列影像和表格說明系統中心 Configuration Manager 整合拓撲中的功能。

![mbam2\-5](images/mbam2-5-cmcomponents.png)

**重要**  
在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供自助服務 Web 服務，其中的 MBAM 用戶端、管理和監控網站，以及自助式入口網站直接與恢復資料庫進行通訊。

**警告**  
因為 MBAM 用戶端和網站直接與復原資料庫通訊，所以在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中已不再提供監視 Web 服務。


|                        功能類型                        |                                                                                                    描述                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    自助服務伺服器                     |                                                                                                                                                                                                                   |
|                  自助服務 Web 服務                  |                                                 此 web 服務是由 MBAM 用戶端和自助入口網站使用，以與恢復資料庫進行通訊。                                                  |
|                    自助服務網站                    |                          此網站可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。                          |
| 管理和監控伺服器/復原審核報告 |                                                                                                                                                                                                                   |
|         管理和監控 Web 服務          |                               此 web 服務可讓您在管理與監控網站以及儲存報告資料的 SQL Server 資料庫之間進行通訊。                               |
|           管理和監控網站            | [恢復審核] 報告是透過 [管理] 和 [監視] 網站查看。 使用 Configuration Manager 主控台來查看所有其他報表，或直接從 SQL Server Reporting Services 查看報表。 |
|                         資料庫                          |                                                                                                                                                                                                                   |
|                     復原資料庫                      |                                                                 此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。                                                                  |
|                       審核資料庫                       |                                                                   此資料庫儲存有關恢復嘗試與活動的審核資訊。                                                                    |
|               Configuration Manager 功能               |                                                                                                                                                                                                                   |
|          Configuration Manager 管理主控台          |                                                                   這個主控台內嵌于 Configuration Manager 中，用來查看報告。                                                                   |
|               Configuration Manager 報告                |                                                             報告顯示企業中用戶端電腦的合規性與復原審核資料。                                                              |
|               SQL Server Reporting Services                |                                                SSRS 會啟用 MBAM 報告。 報告可以直接從 SSRS 或從 Configuration Manager 主控台查看。                                                 |

## 相關主題

[MBAM 2.5 的概要架構](high-level-architecture-for-mbam-25.md)

[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




