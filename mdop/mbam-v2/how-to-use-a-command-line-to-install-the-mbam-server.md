---
title: 如何使用命令列安裝 MBAM 伺服器
description: 如何使用命令列安裝 MBAM 伺服器
author: dansimp
ms.assetid: 6ffc6d41-a793-42c2-b997-95ba47550648
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a689a2df77300300073b2731281004feac87305f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811277"
---
# 如何使用命令列安裝 MBAM 伺服器


您可以使用命令列，透過獨立或 Configuration Manager 拓撲來安裝 MBAM 伺服器。 下列命令列範例是用於在單一伺服器上部署 MBAM，這是一個只能在測試環境中使用的架構。 當您將 MBAM 部署至生產環境時，您需要變更命令列，這應該有多個伺服器。

## 用獨立拓朴部署 MBAM 2.0 伺服器的命令列


您可以使用類似下列的命令列，以獨立拓朴來安裝 MBAM 伺服器。

``` syntax
MbamSetup.exe /qb /l*v MaltaServerInstall.log TOPOLOGY=0 I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 ADDLOCAL=KeyDatabase,ReportsDatabase,Reports,AdministrationMonitoringServer,SelfServiceServer,PolicyTemplate,REPORTS_USERACCOUNT=[UserDomain]\[UserName1] REPORTS_USERACCOUNTPW=[UserPwd1] COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

下表說明用獨立拓朴部署 MBAM 伺服器的命令列參數。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">參數值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>技術</p></td>
<td align="left"><p>0</p></td>
<td align="left"><p>0–獨立拓朴</p></td>
</tr>
<tr class="even">
<td align="left"><p>I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</p></td>
<td align="left"><p>01</p></td>
<td align="left"><p>0–不接受授權 agreement1 –接受授權協定</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ADDLOCAL</p></td>
<td align="left"><p></p></td>
<td align="left"><p>要在伺服器上安裝的功能</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>KeyDatabase</p></td>
<td align="left"><p>復原資料庫</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>ReportsDatabase</p></td>
<td align="left"><p>合規性和審核報告資料庫</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>報告</p></td>
<td align="left"><p>合規性與審計報告</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>AdministrationMonitoringServer</p></td>
<td align="left"><p>管理和監控網站</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>SelfServiceServer</p></td>
<td align="left"><p>自助服務入口網站</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>PolicyTemplate</p></td>
<td align="left"><p>MBAM 群組原則範本</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTS_USERACCOUNT</p></td>
<td align="left"><p>[UserDomain][UserName1]</p></td>
<td align="left"><p>可存取合規性和審核資料庫之 Reporting Services 服務帳戶的網域和使用者帳戶</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTS_USERACCOUNTPW</p></td>
<td align="left"><p>[UserPwd1]</p></td>
<td align="left"><p>可存取合規性和審核資料庫之 Reporting Services 服務帳戶的密碼</p></td>
</tr>
<tr class="even">
<td align="left"><p>COMPLIDB_SQLINSTANCE</p></td>
<td align="left"><p>名稱</p></td>
<td align="left"><p>合規性和審核資料庫的 SQL Server 實例名稱– <strong> 將% computername% 替換 </strong> 為電腦名稱稱</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RECOVERYANDHWDB_SQLINSTANCE</p></td>
<td align="left"><p>名稱</p></td>
<td align="left"><p>針對復原資料庫的 SQL Server 實例名稱– <strong> 將% computername% 替換 </strong> 為電腦名稱稱</p></td>
</tr>
<tr class="even">
<td align="left"><p>SRS_INSTANCENAME</p></td>
<td align="left"><p>名稱</p></td>
<td align="left"><p>要安裝合規性和審核報告的 SQL Server Reporting Server 實例–將 <strong> % computername% 替換 </strong> 為電腦名稱稱</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ADMINANDMON_WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>管理和監視網站的埠;"83" 只是範例</p></td>
</tr>
<tr class="even">
<td align="left"><p>WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>自助服務入口網站的埠;"83" 只是範例</p></td>
</tr>
</tbody>
</table>

 

## 用 Configuration Manager 拓撲部署 MBAM 2.0 伺服器的命令列


您可以使用類似下列的命令列來安裝 MBAM 伺服器與 Configuration Manager 拓撲。

``` syntax
MbamSetup.exe /qn /l*v MaltaServerInstall.log I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 TOPOLOGY=1 COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% REPORTS_USERACCOUNT=[UserDomain]\[UserName] REPORTS_USERACCOUNTPW=[UserPwd] ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

下表說明用 Configuration Manager 拓撲來安裝 MBAM 2.0 伺服器的命令列參數。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">參數值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>技術</p></td>
<td align="left"><p>sr-1</p></td>
<td align="left"><p>1-Configuration Manager 拓撲</p></td>
</tr>
<tr class="even">
<td align="left"><p>I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</p></td>
<td align="left"><p>01</p></td>
<td align="left"><p>0–不接受授權 agreement1 –接受授權協定</p></td>
</tr>
<tr class="odd">
<td align="left"><p>COMPLIDB_SQLINSTANCE</p></td>
<td align="left"><p>名稱</p></td>
<td align="left"><p>審核資料庫的 SQL Server 實例名稱– <strong> 將% computername% 替換 </strong> 為電腦名稱稱</p></td>
</tr>
<tr class="even">
<td align="left"><p>RECOVERYANDHWDB_SQLINSTANCE</p></td>
<td align="left"><p>名稱</p></td>
<td align="left"><p>恢復資料庫的 SQL Server 實例名稱- <strong> </strong> 以電腦名稱稱取代% computername%</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SRS_INSTANCENAME</p></td>
<td align="left"><p>名稱</p></td>
<td align="left"><p>要安裝審計報告的 SQL Server Reporting Server 實例–將% computername% 替換為電腦名稱稱</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTS_USERACCOUNT</p></td>
<td align="left"><p>[UserDomain][UserName1]</p></td>
<td align="left"><p>可存取合規性和審核資料庫之 Reporting Services 服務帳戶的網域和使用者帳戶</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTS_USERACCOUNTPW</p></td>
<td align="left"><p>[UserPwd1]</p></td>
<td align="left"><p>可存取合規性和審核資料庫之 Reporting Services 服務帳戶的密碼</p></td>
</tr>
<tr class="even">
<td align="left"><p>ADMINANDMON_WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>管理和監視網站的埠;"83" 只是範例</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>自助服務入口網站的埠;"83" 只是範例</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





