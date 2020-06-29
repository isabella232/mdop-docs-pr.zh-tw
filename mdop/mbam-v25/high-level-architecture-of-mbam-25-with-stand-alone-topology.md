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
ms.openlocfilehash: 75e878e24b4675f2f2f574791d0f06ecadd0196d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811828"
---
# MBAM 2.5 搭配獨立拓撲的概要架構


本主題描述使用 Configuration Manager 獨立拓朴部署 Microsoft BitLocker 管理和監控（MBAM）的建議架構。 在這個拓朴中，MBAM 是作為獨立產品進行部署。 您也可以使用 Configuration Manager 整合拓朴來部署 MBAM，並將 MBAM 與 Configuration Manager 整合在一起。 如需詳細資訊，請參閱[含 Configuration Manager 整合拓朴的 MBAM 2.5 高層架構](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。

如需本主題中所述軟體支援版本的清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。

**記事** 我們建議您只在測試環境中使用單一伺服器結構。

 

## 建議的伺服器數和支援的用戶端數量


在生產環境中，建議的伺服器數量及支援的用戶端數量如下：

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
<td align="left"><p>伺服器和其他電腦的數目</p></td>
<td align="left"><p>兩個伺服器</p>
<p>一個工作站</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的用戶端電腦數目</p></td>
<td align="left"><p>500000</p></td>
</tr>
</tbody>
</table>

 

## 使用獨立拓朴的建議 MBAM 高層次架構


下列圖表和表格描述了建議的高層次、雙伺服器架構，以供獨立拓朴 MBAM 使用。 MBAM 多林部署需要單向或雙向信任。 單向信任要求伺服器網域信任用戶端網域。

![mbam2](images/mbam2-5-2servers.png)

在此伺服器上設定的伺服器功能說明資料庫伺服器

合規性和審核資料庫

此功能已在執行 Windows Server 和支援的 SQL Server 實例的伺服器上設定。

**合規性和審核資料庫**會儲存規範資料，主要用於 SQL Server Reporting Services 主機的報表。

復原資料庫

此功能已在執行 Windows Server 和支援的 SQL Server 實例的伺服器上設定。

復原**資料庫**會儲存從 MBAM 用戶端電腦收集的復原資料。

報告

此功能已在執行 Windows Server 和支援的 SQL Server 實例的伺服器上設定。

**報告**會提供企業中用戶端電腦的復原審核及合規性狀態資料。 您可以從 [管理] 和 [監視] 網站或直接從 SQL Server Reporting Services 存取報表。

管理和監控伺服器

管理和監控網站

此功能是在執行 Windows Server 的電腦上設定。

**管理和監控網站**是用來：

-   當使用者鎖定時，協助使用者重新取得電腦存取權。（此網站區域通常稱為 [技術支援中心]。）

-   查看顯示用戶端電腦合規性狀態與復原活動的報告。

自助服務入口網站

此功能是在執行 Windows Server 的電腦上設定。

**自助式入口**網站是一種網站，可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。

監視此網站的 web 服務

此功能是在執行 Windows Server 的電腦上設定。

MBAM 用戶端和網站會使用**監視 web 服務**來與資料庫進行通訊。

**重要** 在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供監視 Web 服務，因為 MBAM 網站會直接與恢復資料庫通訊。

 

管理工作站

MBAM 群組原則範本

-   MBAM 群組原則範本是定義 MBAM 之實現設定的群組原則設定，可讓您管理 BitLocker 磁碟機加密。

-   在執行 MBAM 之前，您必須從[如何取得 MDOP 組原則（admx）範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載群組原則範本，並將其複製到執行支援的 Windows Server 或 Windows 作業系統的伺服器或工作站。

-   工作站不一定是專用電腦。

MBAM 用戶端與 Configuration Manager 用戶端電腦

MBAM 用戶端軟體

MBAM 用戶端：

-   使用群組原則物件，在企業中的用戶端電腦上強制執行 BitLocker 磁碟機加密。

-   收集三種資料磁片磁碟機類型的 Bitlocker 復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動（USB）資料磁碟機。

-   收集用戶端電腦的恢復資訊和電腦資訊。



## 相關主題


[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

[MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[MBAM 2.5 部署的功能圖例](illustrated-features-of-an-mbam-25-deployment.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





