---
title: 安裝 APP-V 5.x Server 之前先查看登錄機碼
description: 安裝 APP-V 5.x Server 之前先查看登錄機碼
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.openlocfilehash: 9fe5a1b37d0fb5208d138939bb2fc79c89171fb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800661"
---
# 安裝 APP-V 5.x Server 之前先查看登錄機碼

如果您要從 App-v 5.0 SP1 修復程式套件3或更新版本升級 app-v Server，請先完成本節中的步驟，再安裝應用程式-V 5 a.x 伺服器

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>需要此步驟時</strong></p></td>
<td align="left"><p>您要從 App-v 5.0 SP1 升級到您使用 .msp 檔案安裝的任何後續修復程式套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>哪些元件需要您執行此步驟</strong></p></td>
<td align="left"><p>僅限您要升級的 App-v Server 元件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>當您需要執行此步驟時</strong></p></td>
<td align="left"><p>將 app-v Server 升級到 App 之前，請先將 App-v 伺服器升級至 App-v</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>您需要執行的動作</strong></p></td>
<td align="left"><p>使用下清單格中的資訊， <code>HKLM\Software\Microsoft\AppV\Server</code> 以您在原始伺服器安裝中所提供的值來更新每個登錄項的值。 完成此步驟會還原在安裝 App-v 5.0 SP1 修復程式套件時可能已移除的註冊表值。</p></td>
</tr>
</tbody>
</table>

 

**ManagementDatabase 鍵**

如果您要安裝管理資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>說明是否需要公用存取帳戶才能存取非本地管理資料庫。 如果需要，值會設定為 "1"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_NAME</p></td>
<td align="left"><p>管理資料庫的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用於讀取（公開）管理資料庫存取權的帳戶。</p>
<p>在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用來讀取（公開）管理資料庫存取權的帳戶的安全識別碼（SID）。</p>
<p>在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理資料庫的 SQL Server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用於寫入管理資料庫（系統管理員）存取權的帳戶。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用來撰寫（系統管理員）存取管理資料庫之帳戶的安全識別碼（SID）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>管理伺服器遠端電腦帳戶（[域 \ 帳戶]）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>管理伺服器（域 \ 帳戶）的安裝管理員登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有效值如下：</p>
<ul>
<li><p><strong>1 </strong> -此管理服務是在本機電腦上，也就是 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 是空白的。</p></li>
<li><p><strong>0 </strong> - 管理服務與本機電腦位於不同的電腦上。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**ManagementService 鍵**

如果您要安裝管理伺服器，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MANAGEMENT_ADMINACCOUNT</p></td>
<td align="left"><p>已授權管理 App-v （網域 \ 帳戶）的 Active Directory 網域服務（AD DS）群組或帳戶。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>包含管理資料庫的 SQL server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>包含管理資料庫的遠端 SQL 伺服器名稱。</p>
<p>如果此值為空白，則會使用本機電腦。</p></td>
</tr>
</tbody>
</table>

 

**ReportingDatabase 鍵**

如果您要安裝報告資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>說明存取非本地報告資料庫是否需要公用存取帳戶。 如果需要，值會設定為 "1"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_NAME</p></td>
<td align="left"><p>報告資料庫的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用於讀取（公開）存取報表資料庫的帳戶。</p>
<p>在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>帳戶的安全識別碼（SID），用於讀取（公開）的報表資料庫存取權。</p>
<p>在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>報表資料庫的 SQL Server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>報表伺服器遠端電腦帳戶（[域 \ 帳戶]）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>報表服務器（域 \ 帳戶）的安裝管理員登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有效值如下：</p>
<ul>
<li><p><strong>1 </strong> -報表服務位於本機電腦上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 為空白。</p></li>
<li><p><strong>0 </strong> - 報表服務與本機電腦在不同的電腦上。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**ReportingService 鍵**

如果您要安裝報表伺服器，請在中設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引鍵名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>報表資料庫的 SQL Server 實例。</p>
<p>如果該值為空白，則會使用預設的資料庫實例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>具有報告資料庫之遠端 SQL 伺服器的名稱。</p>
<p>如果此值為空白，則會使用本機電腦。</p></td>
</tr>
</tbody>
</table>

