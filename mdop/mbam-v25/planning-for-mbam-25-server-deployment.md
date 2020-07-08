---
title: MBAM 2.5 伺服器部署規劃
description: MBAM 2.5 伺服器部署規劃
author: dansimp
ms.assetid: 88774c89-31c8-4eb8-a845-a00bbec8c870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2ecb510fab821118ce210577f9ffb83c39be050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811619"
---
# MBAM 2.5 伺服器部署規劃


本主題列出您針對 MBAM 獨立版與 Configuration Manager 拓撲所部署的功能，並列出您需要的部署順序。 每個拓朴都有建議的配置。 不過，您可以根據您的可伸縮性需求，在不同的配置和多個伺服器上設定 MBAM 伺服器資料庫和功能。

## 兩種拓撲的重要規劃考慮


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">考量</th>
<th align="left">詳細資料或用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>開始進行部署之前，請先檢查下列專案：</p>
<ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></li>
</ul></td>
<td align="left"><p>每個 MBAM 功能都有特定的先決條件，您必須先滿足這些先決條件，才能開始 MBAM 安裝。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 中的 BitLocker 復原金鑰會在單一使用後到期。</p></td>
<td align="left"><p>單一用途代表已透過管理和監控網站（又稱為說明服務台）、自助入口網站或使用 <strong> MbamBitLockerRecoveryKey Windows PowerShell Cmdlet 來檢索復原金鑰 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>追蹤設定每個功能的電腦名稱稱。 您將會在整個配置程式中使用此資訊。</p></td>
<td align="left"><p>您可能會想要使用 <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"> MBAM 2.5 部署檢查清單 </a> 來達到此目的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>只設定 MDOP MBAM （BitLocker 管理）節點中的 [群組原則] 設定。 請勿變更 BitLocker 磁片磁碟機加密節點中的群組原則設定。</p></td>
<td align="left"><p>如果您在 BitLocker 磁片磁碟機加密節點中變更群組原則設定，MBAM 將無法運作。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="planning-for-mbam-server-deployment---stand-alone-topology"></a>規劃 MBAM Server 部署-獨立拓朴


若是獨立拓朴，建議在生產環境中使用雙伺服器設定，雖然您可以使用三至四個伺服器的設定。

MBAM 獨立拓朴的伺服器基礎結構包含下列功能，這些功能必須按照所列的順序進行設定：

1.  資料庫（合規性與審核資料庫及復原資料庫）

2.  報告

3.  Web 應用程式（以及其對應的 web 服務）

    -   管理和監控網站

    -   自助服務入口網站

如需這些功能的描述，請參閱[含獨立拓朴之 MBAM 2.5 的高層次架構](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。

## <a href="" id="planning-for-mbam-server-deployment---configuration-manager-topology"></a>規劃 MBAM Server 部署-Configuration Manager 拓撲


針對 Configuration Manager 整合拓朴，雖然您可以使用其他伺服器的設定，但針對生產環境建議使用三伺服器配置。

MBAM Configuration Manager 拓撲結構的伺服器基礎結構包含下列功能，這些功能必須以所列的順序進行設定或執行：

1.  資料庫（合規性與審核資料庫及復原資料庫）

2.  報告

3.  Web 應用程式（以及其對應的 web 服務）

    -   管理和監控網站

    -   自助服務入口網站

4.  System Center Configuration Manager 整合

如需這些功能的描述，請參閱[含 Configuration Manager 整合拓朴的 MBAM 2.5 高層架構](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。



## 相關主題


[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[部署 MBAM 2.5 伺服器基礎結構](deploying-the-mbam-25-server-infrastructure.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





