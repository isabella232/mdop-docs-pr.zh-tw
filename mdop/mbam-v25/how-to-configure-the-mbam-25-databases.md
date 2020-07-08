---
title: 如何設定 MBAM 2.5 資料庫
description: 如何設定 MBAM 2.5 資料庫
author: dansimp
ms.assetid: 66e1c81b-f785-4398-9175-bb5f112c2a35
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c11cb58d8fd9266bd0322e4cf9aa96256b7fbb6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811865"
---
# 如何設定 MBAM 2.5 資料庫


本主題說明如何使用以下內容來設定 Microsoft BitLocker 管理和監控（MBAM）2.5 合規性與審核資料庫及復原資料庫

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
<td align="left"><p>在您規劃設定 MBAM 伺服器功能的每個伺服器上，安裝 MBAM Server 軟體。</p>
<div class="alert">
<strong>注意</strong><br/><p>您可以使用 Windows PowerShell 或匯出的資料層應用程式（DAC）套件，將資料庫安裝至遠端 SQL Server 電腦。 如需有關 DAC 套件的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 資料層應用程式 </a> 。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>如果您打算使用 Windows powershell Cmdlet 來設定 MBAM 伺服器功能，請參閱使用 Windows PowerShell 的先決條件。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
</tr>
</tbody>
</table>



**使用 Windows PowerShell 來設定資料庫**

1.  開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。

2.  使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 來設定資料庫。 若要取得有關這個 Windows PowerShell Cmdlet 的資訊，請輸入**Get-help Enable-MbamDatabase**。

**使用嚮導來設定合規性和審核資料庫**

1. 在您想要設定資料庫的伺服器上，啟動 [ **MBAM 伺服器**設定] 嚮導。 您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。

2. 按一下 [**新增功能**]、選取 [**合規性] 和 [審核資料庫****及復原資料庫**]，然後按一下 **[下一步]**。 嚮導會檢查資料庫的所有先決條件是否都已滿足。

3. 如果先決條件檢查成功，請按 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後**再次按一下 [檢查先決條件**]。

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
   <td align="left"><p><strong>SQL Server 名稱</strong></p></td>
   <td align="left"><p>您正在設定合規性和審核資料庫之伺服器的名稱。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>您必須在合規性和審核資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。 預設埠號碼是1433。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server 資料庫實例</strong></p></td>
   <td align="left"><p>儲存合規性和審核資料之資料庫實例的名稱。 您也必須指定資料庫資訊的位置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>資料庫名稱</strong></p></td>
   <td align="left"><p>儲存合規性資料之資料庫的名稱。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果您是從舊版 MBAM 升級，您必須使用與先前部署中所使用的名稱相同的資料庫名稱。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>讀/寫存取網域使用者或群組</strong></p></td>
   <td align="left"><p>擁有此資料庫讀/寫許可權的網域使用者或群組，可讓 web 應用程式存取此資料庫中的資料和報表。</p>
   <p>如果您在此欄位中輸入使用者，其值必須與 <strong> </strong> [ <strong> 設定 web 應用程式] 頁面上的 [web 服務應用程式池網域帳戶] 欄位中的值相同 </strong> 。</p>
   <p>如果您在此欄位中輸入群組，則 [ <strong> 設定 Web 應用程式] 頁面上的 [Web 服務應用程式群組網域帳戶] 欄位中的值 </strong> <strong> </strong> 必須是您在這個欄位中輸入之群組的成員。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>唯讀存取網域使用者或群組</strong></p></td>
   <td align="left"><p>將對此資料庫擁有唯讀許可權的使用者或群組的名稱，以讓報告能夠存取此資料庫中的合規性資料。</p>
   <p>如果您在此欄位中輸入使用者，該使用者必須是您在 <strong> </strong> [設定報告] 頁面上的 [合規性和審核資料庫網域帳戶] 欄位中所指定的使用者 <strong> </strong> 。</p>
   <p>如果您在此欄位中輸入群組，您在 <strong> [設定報告] 頁面上的 [合規性與審計資料庫網域帳戶] 欄位中所指定的值， </strong> <strong> </strong> 必須是您在此欄位中指定之群組的成員。</p></td>
   </tr>
   </tbody>
   </table>



5. 請繼續閱讀下一節，以設定復原資料庫。

**使用嚮導來設定恢復資料庫**

1. 使用下列說明，在嚮導中輸入欄位值：

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
   <td align="left"><p><strong>SQL Server 名稱</strong></p></td>
   <td align="left"><p>您正在設定復原資料庫的伺服器名稱。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>您必須在恢復資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。 預設埠號碼是1433。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server 資料庫實例</strong></p></td>
   <td align="left"><p>儲存恢復資料之資料庫實例的名稱。 您也必須指定資料庫資訊的位置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>資料庫名稱</strong></p></td>
   <td align="left"><p>儲存修復資料之資料庫的名稱。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果您是從舊版 MBAM 升級，您必須使用與先前部署中所使用的名稱相同的資料庫名稱。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>讀/寫存取網域使用者或群組</strong></p></td>
   <td align="left"><p>擁有此資料庫讀/寫許可權的網域使用者或群組，可讓 web 應用程式存取此資料庫中的資料和報表。</p>
   <p>如果您在此欄位中輸入使用者，其值必須與 <strong> </strong> [ <strong> 設定 web 應用程式] 頁面上的 [web 服務應用程式池網域帳戶] 欄位中的值相同 </strong> 。</p>
   <p>如果您在此欄位中輸入群組，則 [ <strong> 設定 Web 應用程式] 頁面上的 [Web 服務應用程式群組網域帳戶] 欄位中的值 </strong> <strong> </strong> 必須是您在這個欄位中輸入之群組的成員。</p></td>
   </tr>
   </tbody>
   </table>



2. 完成專案後，請按 **[下一步**]。

   嚮導會檢查資料庫的所有先決條件是否都已滿足。

3. 如果先決條件檢查成功，請按 **[下一步]** 繼續。 否則，請解決任何缺少的先決條件，然後再按**一次 [下一步]** 。

4. 在 [**摘要**] 頁面上，查看將新增的功能。

   **注意**  
   若要建立您剛剛建立之專案的 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**]，然後儲存腳本。



5. 按一下 [**新增**]，在伺服器上新增 MBAM 資料庫，然後按一下 [**關閉**]。



## 相關主題


[伺服器事件記錄檔](server-event-logs.md)

[設定 MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)

[如何設定 MBAM 2.5 報告](how-to-configure-the-mbam-25-reports.md)

[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)

[驗證 MBAM 2.5 伺服器功能設定](validating-the-mbam-25-server-feature-configuration.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





