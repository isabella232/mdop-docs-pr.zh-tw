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
ms.openlocfilehash: 139980fb6712b40685a41bab45610da670803afa
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910618"
---
# <a name="illustrated-features-of-an-mbam-25-deployment"></a>MBAM 2.5 部署的功能圖例


本主題說明適用于下列拓撲的 Microsoft BitLocker 系統管理與監控 (管理與監控) 2.5 部署：

-   獨立式管理

-   System Center Configuration Manager集成

**重要**  
這些功能並不代表部署 MM 的建議架構。 請僅以此資訊做為指南，瞭解由一個管理及管理管理計畫所建立之個別功能。 請參閱 [適用于 2.5 的高層級架構，](high-level-architecture-for-mbam-25.md) 以瞭解適用于該架構的推薦架構。



有關本主題中提及的軟體支援版本清單，請參閱[適用于支援的組配置。](mbam-25-supported-configurations.md)

## <a name="mbam-stand-alone-topology"></a><a href="" id="bkmk-standalone"></a> 獨立拓撲


下圖和表格說明一個 INM 獨立拓撲中的功能。

![mbab2\-5。](images/mbam2-5-standalonecomponents.png)

|功能類型|描述|資料庫|
|-|-|-|
|修復資料庫|此資料庫會儲存從 SQLM 用戶端電腦收集的修復資料。|這項功能是在伺服器執行伺服器Windows和支援的 SQL Server實例上。|
|合規性與稽核資料庫|此資料庫會儲存合規性資料，這些資料主要用於主機SQL Server Reporting Services報表。|這項功能是在伺服器執行伺服器Windows和支援的 SQL Server實例上。|
|合規性和稽核報告|||
|報告 Web 服務|此 Web 服務可讓系統管理與監控網站與儲存報表資料SQL Server實例之間的通訊。|這項功能會安裝在執行伺服器Windows伺服器上。|
|報告網站 (系統管理與監控網站) |您從系統管理與監控網站查看報告。 報告會提供企業用戶端電腦的修復稽核和合規性狀態資料。|此功能是在執行伺服器伺服器Windows上。|
|SQL Server Reporting Services (SSRS) |報表在 SSRS 資料庫實例中已配置。 您可以直接從 SSRS 或系統管理與監控網站來查看報告。|此功能是在執行 SSRS 的伺服器上Windows伺服器，以及SQL Server SSRS 的受支援實例。|
|Self-Service伺服器|||
|Self-Service Web 服務|此 Web 服務會由管理與監控網站及 Self-Service網站使用，以與修復資料庫通訊。|這項功能會安裝在執行伺服器Windows電腦上安裝。|
|Self-Service網站 (自助入口網站) |這個網站可讓用戶端電腦上的使用者獨立地登錄網站，以取得修復金鑰 ，如果他們失去或忘記 BitLocker 密碼。|此功能是在執行伺服器的電腦上Windows。|
|系統管理與監控伺服器|||
|系統管理與監控 Web 服務|監控 Web 服務會由管理與資料庫通訊的一部分，由該客戶與網站使用。|這項功能會安裝在執行伺服器Windows電腦上安裝。|

**重要**  
microsoft BitLocker 系統管理與監控 (的) 2.5 SP1 中不再提供 Self-Service Web 服務，其中，MICROSOFT BITLocker 用戶端、系統管理與監控網站及 Self-Service 入口網站會直接與修復資料庫通訊。

**重要**  
Microsoft BitLocker 系統管理與監控 () 2.5 SP1 不再提供監控 Web 服務，因為 MICROSOFT BitLocker 用戶端和網站會直接與修復資料庫通訊。


## <a name="system-center-configuration-manager-integration-topology"></a><a href="" id="bkmk-cmintegrated"></a>System Center Configuration Manager整合拓撲

下圖和表格說明整合拓撲System Center Configuration Manager功能。

![5。](images/mbam2-5-cmcomponents.png)

**重要**  
microsoft BitLocker 系統管理與監控 (的) 2.5 SP1 中不再提供 Self-Service Web 服務，其中，MICROSOFT BITLocker 用戶端、系統管理與監控網站及 Self-Service 入口網站會直接與修復資料庫通訊。

**警告**  
Microsoft BitLocker 系統管理與監控 () 2.5 SP1 不再提供監控 Web 服務，因為 MICROSOFT BitLocker 用戶端和網站會直接與修復資料庫通訊。


|                        功能類型                        |                                                                                                    描述                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Self-Service伺服器                     |                                                                                                                                                                                                                   |
|                  Self-Service Web 服務                  |                                                 此 Web 服務會由 Self-Service 用戶端和入口網站使用，以與修復資料庫通訊。                                                  |
|                    Self-Service網站                    |                          這個網站可讓用戶端電腦上的使用者獨立地登錄網站，以取得修復金鑰 ，如果他們失去或忘記 BitLocker 密碼。                          |
| 系統管理與監控伺服器/修復稽核報告 |                                                                                                                                                                                                                   |
|         系統管理與監控 Web 服務          |                               此 Web 服務可讓系統管理與監控網站與SQL Server資料儲存之資料庫之間的通訊。                               |
|           系統管理與監控網站            | 系統從系統管理與監控網站查看修復稽核報告。 使用 Configuration Manager 主控台來查看所有其他報表，或直接從 SQL Server Reporting Services。 |
|                         資料庫                          |                                                                                                                                                                                                                   |
|                     修復資料庫                      |                                                                 此資料庫會儲存從 SQLM 用戶端電腦收集的修復資料。                                                                  |
|                       稽核資料庫                       |                                                                   此資料庫會儲存有關修復嘗試和活動的稽核資訊。                                                                    |
|               Configuration Manager 功能               |                                                                                                                                                                                                                   |
|          Configuration Manager 管理主控台          |                                                                   此主控台內建于 Configuration Manager 中，可用來查看報表。                                                                   |
|               Configuration Manager 報表                |                                                             報告會顯示您企業用戶端電腦的合規性及修復稽核資料。                                                              |
|               SQL Server Reporting Services                |                                                SSRS 會啟用 <管理與管理報告>。 可以直接從 SSRS 或 Configuration Manager 主控台來查看報表。                                                 |

## <a name="related-topics"></a>相關主題

[MBAM 2.5 的概要架構](high-level-architecture-for-mbam-25.md)

[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

## <a name="got-a-suggestion-for-mbam"></a>有關于 MM 的建議嗎？
- 在這裡新增或投票支援 [建議](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- 針對針對的 MM 問題，請使用[的是 ：。。](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)




