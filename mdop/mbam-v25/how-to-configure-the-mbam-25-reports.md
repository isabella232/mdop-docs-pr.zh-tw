---
title: 如何設定 MBAM 2.5 報告
description: 如何設定 MBAM 2.5 報告
author: dansimp
ms.assetid: ec462879-0253-4d9c-83c7-a9bcad479725
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b372bd6bc38a3729aef43354ecf19b2619b7856
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811864"
---
# 如何設定 MBAM 2.5 報告


本主題說明如何使用以下內容來設定 Microsoft BitLocker 管理和監控（MBAM）2.5 報告功能：

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
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 的概要架構</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>查看 MBAM 支援的設定。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在每個伺服器上完成必要的先決條件。</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 必備元件 </a> （如果適用）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在您規劃設定 MBAM 伺服器功能的每個伺服器上，安裝 MBAM Server 軟體。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果您打算使用 Windows powershell Cmdlet 來設定 MBAM 伺服器功能，請參閱使用 Windows PowerShell 的先決條件。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 來設定報表**

1.  開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。

2.  使用**Enable-MbamReport** Windows PowerShell Cmdlet 來設定報告。 若要取得有關這個 Windows PowerShell Cmdlet 的資訊，請輸入**Get-help Enable-MbamReport**。

**使用嚮導來設定報表**

1. 在您想要設定報告的伺服器上，啟動 [ **MBAM 伺服器**設定] 嚮導。 您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。

2. 按一下 [**新增功能**]，選取 [**報表**]，然後按一下 **[下一步]**。 嚮導會檢查是否符合報表的所有先決條件。

3. 按 \[**下一步**\] 繼續。

4. 使用下列說明，在嚮導中輸入欄位值：

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
   <td align="left"><p><strong>SQL Server Reporting Services 實例</strong></p></td>
   <td align="left"><p>將設定報告的 SQL Server Reporting Services 實例。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>報告角色網域群組</strong></p></td>
   <td align="left"><p>其成員有權存取管理和監視伺服器上報告的網域使用者群組的名稱。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server 名稱</strong></p></td>
   <td align="left"><p>已設定合規性和審核資料庫之伺服器的名稱。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server 資料庫實例</strong></p></td>
   <td align="left"><p>在 <em> </em> 其中設定合規性和審核資料庫之 SQL Server 實例（例如，MSSQLSERVER）的名稱。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>您必須在報表電腦上新增例外狀況，才能在報表伺服器的埠上啟用輸入流量（預設埠為80）。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>資料庫名稱</strong></p></td>
   <td align="left"><p>合規性和審核資料庫的名稱。 根據預設，資料庫名稱是 <strong> MBAM 合規性狀態 </strong> ，不過您可以在設定合規性和審核資料庫時變更名稱。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果您是從舊版 MBAM 升級，您必須使用與先前部署中所使用之名稱相同的資料庫名稱。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>合規性與審計資料庫網域帳戶</strong></p></td>
   <td align="left"><p>[網域使用者帳戶和密碼] 來存取合規性和審核資料庫。</p>
   <p>如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是使用者，則您必須在這個欄位中輸入相同的值。</p>
   <p>如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是群組，則您在這個欄位中輸入的值必須是該群組的成員。</p>
   <p>將此帳戶的密碼設定為永不過期。 使用者帳戶應該能夠存取 MBAM [報告使用者] 群組提供的所有資料。</p></td>
   </tr>
   </tbody>
   </table>



5. 完成專案後，請按 **[下一步**]。

   嚮導會檢查是否已符合報表功能的所有先決條件。

6. 按 \[**下一步**\] 繼續。

7. 在 [**摘要**] 頁面上，查看將新增的功能。

   **注意**  
   若要建立您剛剛建立之專案的 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**]，然後儲存腳本。



8. 按一下 [**新增**]，在伺服器上新增報表，然後按一下 [**關閉**]。



## 相關主題


[伺服器事件記錄檔](server-event-logs.md)

[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)

[驗證 MBAM 2.5 伺服器功能設定](validating-the-mbam-25-server-feature-configuration.md)


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






