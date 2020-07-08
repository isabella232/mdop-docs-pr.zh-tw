---
title: 如何設定 MBAM 2.5 System Center Configuration Manager 整合
description: 如何設定 MBAM 2.5 System Center Configuration Manager 整合
author: dansimp
ms.assetid: 2b8a4c13-1dad-41e8-89ac-6889c5f7e051
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c6fb0a0b06399baf1dc6493a40d17e76a51741f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800095"
---
# 如何設定 MBAM 2.5 System Center Configuration Manager 整合


本主題說明如何設定 Microsoft BitLocker 管理與監視（MBAM），以使用系統中心 Configuration Manager 整合拓朴，將 MBAM 與 Configuration Manager 整合。

這些指示說明如何使用以下專案來設定 Configuration Manager 整合：

-   Windows PowerShell Cmdlet

-   [MBAM 伺服器設定] 嚮導

指示是以[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)中的建議架構為基礎。

**開始設定前：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">取得指示的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>針對 MBAM 查看建議的架構。</p></td>
<td align="left"><p><a href="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md" data-raw-source="[High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)">MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>查看 MBAM 支援的設定。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在每個伺服器上完成必要的先決條件。</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在您要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</p>
<div class="alert">
<strong>注意</strong><br/><p>針對此拓朴，您必須在安裝 MBAM Server 軟體的電腦上安裝 Configuration Manager 主控台。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>審查 Windows PowerShell 先決條件（只有在您要使用 Windows PowerShell Cmdlet 來設定 MBAM）時才適用。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 來設定 Configuration Manager 整合**

1.  開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。

2.  使用**Enable-MbamCMIntegration** Windows PowerShell Cmdlet 來設定報告。 若要取得此 Cmdlet 的相關資訊，請輸入**Get-help Enable-MbamCMIntegration**。

**使用嚮導設定系統中心 Configuration Manager 整合**

1.  在您想要設定 System Center Configuration Manager 整合功能的伺服器上，啟動 [MBAM 伺服器設定] 嚮導。 您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。

2.  按一下 [**新增功能**]，選取 [ **System Center Configuration Manager 整合**]，然後按一下 **[下一步]**。

    嚮導會檢查是否符合 Configuration Manager 整合的所有先決條件。

3.  如果先決條件檢查成功，請按 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後**再次按一下 [檢查先決條件**]。

4.  使用下列描述在嚮導中輸入欄位值：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">欄位</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>SQL Server Reporting Services 伺服器</strong></p></td>
    <td align="left"><p>具有 Reporting Services point 角色之伺服器的完整功能變數名稱（FQDN）。 這是部署 MBAM Configuration Manager 報告的伺服器。</p>
    <p>如果您沒有指定伺服器，Configuration Manager 報告將會部署到本機伺服器。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server Reporting Services 實例</strong></p></td>
    <td align="left"><p>部署 Configuration Manager 報表之 SQL Server Reporting Services （SSRS）實例的名稱。</p>
    <p>如果您沒有指定實例，Configuration Manager 報告將會部署到預設的 SSRS 實例名稱。 如果伺服器已安裝 System Center 2012 Configuration Manager，則會忽略您輸入的值。</p></td>
    </tr>
    </tbody>
    </table>



5.  在 [**摘要**] 頁面上，查看將新增的功能。

    **注意**  
    若要建立您剛建立的專案的 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**] 並儲存腳本。



6.  按一下 [**新增**]，將 Configuration Manager 整合功能新增至伺服器，然後按一下 [**關閉**]。



## 相關主題


[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

[驗證 MBAM 2.5 伺服器功能設定](validating-the-mbam-25-server-feature-configuration.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






