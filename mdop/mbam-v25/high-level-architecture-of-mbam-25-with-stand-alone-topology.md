---
title: MBAM 2.5 搭配獨立拓撲的概要架構
description: MBAM 2.5 搭配獨立拓撲的概要架構
author: dansimp
ms.assetid: 35f8c5f6-8be3-443d-baf0-56d68b08f3bc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9ec9b1e4391fde3083564f34b5f89d1c5bd174f7
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910668"
---
# <a name="high-level-architecture-of-mbam-25-with-stand-alone-topology"></a>MBAM 2.5 搭配獨立拓撲的概要架構


本主題說明使用 Configuration Manager 獨立拓撲 (部署 MICROSOFT BitLocker 系統管理與監控) 的架構。 在此拓撲中，將部署為獨立產品。 您也可以使用 Configuration Manager 整合拓撲來部署該拓撲，以將該拓撲與 Configuration Manager 整合。 有關詳細資訊，請參閱使用 Configuration Manager 整合拓撲的[2.5 高層級架構。](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

有關本主題中提及的軟體支援版本清單，請參閱[適用于支援的組配置。](mbam-25-supported-configurations.md)

**注意**  
我們建議您只在測試環境中使用單一伺服器架構。

 

## <a name="recommended-number-of-servers-and-supported-number-of-clients"></a>建議的伺服器數量和支援的用戶端數目


在生產環境中，建議的伺服器數目和支援的用戶端數目如下：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">生產環境中的建議架構</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>伺服器和其他電腦數目</p></td>
<td align="left"><p>兩個伺服器</p>
<p>一個工作站</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的用戶端電腦數目</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## <a name="recommended-mbam-high-level-architecture-with-the-stand-alone-topology"></a>建議的具有獨立拓撲的高層級架構


下列圖表和表格說明建議使用獨立拓撲的適用于 IBMM 的高層、雙伺服器架構。 需要單向或雙向信任的跨林部署。 單向信任要求伺服器網域信任用戶端網域。

![這是一個。](images/mbam2-5-2servers.png)

在此伺服器上設定的伺服器功能描述資料庫伺服器

合規性與稽核資料庫

這項功能是在伺服器伺服器執行Windows，且支援SQL Server實例。

合規性**和稽核資料庫**會儲存合規性資料，這些資料主要用於SQL Server Reporting Services報表。

修復資料庫

這項功能是在伺服器伺服器執行Windows，且支援SQL Server實例。

修復 **資料庫** 會儲存從 SQLM 用戶端電腦收集的修復資料。

報告

這項功能是在伺服器伺服器執行Windows，且支援SQL Server實例。

報告 **會** 提供企業用戶端電腦的修復稽核和合規性狀態資料。 您可以直接從系統管理與監控網站存取SQL Server Reporting Services。

系統管理與監控伺服器

系統管理與監控網站

此功能是在執行伺服器的電腦上Windows。

系統 **管理與監控網站** 用於：

-   協助使用者在鎖定時重新取得電腦存取權。 (網站的這個區域通常稱為技術支援中心。) 

-   查看顯示用戶端電腦合規性狀態及修復活動的報告。

Self-Service入口網站

此功能是在執行伺服器的電腦上Windows。

**自助入口**網站是一個網站，可讓用戶端電腦上的使用者獨立登入網站，以在使用者失去或忘記 BitLocker 密碼時取得修復金鑰。

監控此網站的 Web 服務

此功能是在執行伺服器的電腦上Windows。

**監控 Web 服務**會由管理管理中心用戶端和網站用來與資料庫通訊。

**重要**  
Microsoft BitLocker 系統管理與監控 () 2.5 SP1 中不再提供監控 Web 服務，因為 MICROSOFT BITLocker 網站會直接與修復資料庫通訊。

 

管理工作站

管理與管理管理小群組原則範本

-   此為群組原則設定，可定義用於管理 BitLocker 磁片磁碟機加密的實現設定。

-   執行 IBMM 之前，您必須從如何取得 MDOP 群組原則[ (.admx) 範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載群組原則範本，然後複製到執行支援的 Windows Server 或 Windows 作業系統的伺服器或工作站。

-   工作站不需要是專用電腦。

電腦與 CONFIGURATION Manager 用戶端電腦

管理與管理管理用戶端軟體

該客戶：

-   使用群組原則物件在企業用戶端電腦上強制執行 BitLocker 磁片磁碟機加密。

-   收集三種資料磁碟機類型的 Bitlocker 修復金鑰：作業系統磁片磁碟機、固定資料磁碟機，以及可移除的 USB (資料) 磁片磁碟機。

-   收集用戶端電腦的修復資訊和電腦資訊。



## <a name="related-topics"></a>相關主題


[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

[MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[MBAM 2.5 部署的功能圖例](illustrated-features-of-an-mbam-25-deployment.md)

 

## <a name="got-a-suggestion-for-mbam"></a>有關于 MM 的建議嗎？
- 在這裡新增或投票支援 [建議](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- 針對針對的 MM 問題，請使用[的是 ：。。](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam) 





