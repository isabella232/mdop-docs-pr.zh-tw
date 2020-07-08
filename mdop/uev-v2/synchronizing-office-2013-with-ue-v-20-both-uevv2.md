---
title: 將 Office 2013 與 UE-V 2.0 同步處理
description: 將 Office 2013 與 UE-V 2.0 同步處理
author: dansimp
ms.assetid: c46feb6d-28a8-4799-888d-053531dc5842
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9b079d3f21e6ced689fa2101f5321fa9b1406c8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812026"
---
# 將 Office 2013 與 UE-V 2.0 同步處理


Microsoft 使用者體驗虛擬化（UE-V）2.0 支援使用 UE-V 範本庫中提供的範本來同步處理 Microsoft Office 2013 應用程式設定。 UE-V 2 和 App V 5.0 SP2 支援 Office 2013 專業增強版，在任何 UE-V 啟用的裝置或虛擬化的電腦上，都能在虛擬化的 Office 2013 實例上獲得相同的體驗。

若要啟用 Office 2013 的 UE-V 應用程式設定支援，您可以從[Microsoft 使用者體驗虛擬化（ue-v）2範本庫](https://go.microsoft.com/fwlink/p/?LinkId=246589)下載官方 ue-v Office 2013 範本。 此資源提供 Microsoft 撰寫的 UE-V 設定位置範本，以及社區開發的設定位置範本。

## UE-V 中的 Microsoft Office 支援


UE-V 1.0 和 UE-V 2 包含 Microsoft Office 2010 的設定位置範本。 這些範本是作為 UE-V Agent 安裝程式的一部分進行發佈和註冊。 這些範本可協助在裝置之間同步處理使用者的 Office 體驗。 Office 2013 的 UE-V 範本提供對 Office 2010 範本的非常類似的設定體驗。 在這些設定中不會包含 Office 365 體驗的 Microsoft Office 2013 設定。 如需 Office 365 特定設定的清單，請參閱[office 2013 的使用者和漫遊設定概覽](https://go.microsoft.com/fwlink/p/?LinkId=391220)。

## 已同步處理的 Office 2013 設定


下表包含 UE-V 中 Office 2013 支援的詳細資料：

### Microsoft Office 支援的 UE-V 範本

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">在 UE-V 圖庫上提供的 Office 2013 範本（UE-V 2.0）：</th>
<th align="left">Office 2010 範本（UE-V 1.0 &amp; 1.0 SP1）：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MicrosoftOffice2013Win32.xml</p>
<p>MicrosoftOffice2013Win64.xml</p>
<p>MicrosoftLync2013Win32.xml</p>
<p>MicrosoftLync2013Win64.xml</p></td>
<td align="left"><p>MicrosoftOffice2010Win32.xml</p>
<p>MicrosoftOffice2010Win64.xml</p>
<p>MicrosoftLync2010.xml</p>
<p></p></td>
</tr>
</tbody>
</table>

 

### UE-V 範本支援的 Microsoft Office 應用程式

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Access 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Project 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft Word 2013</p>
<p>Microsoft Office 上傳管理員</p></td>
<td align="left"><p>Microsoft Access 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft OneNote 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft SharePoint Designer 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft Word 2010</p>
<p></p></td>
</tr>
</tbody>
</table>

 

## 部署 Office 2013 範本


您可以使用下列方法來部署 UE-V 設定位置範本：

-   透過**PowerShell 註冊範本**。 如果您使用 Windows PowerShell 來管理電腦，請執行下列 Windows PowerShell 命令以系統管理員的身分開啟，以註冊此設定位置範本：

    ``` syntax
    Register-UevTemplate -Path <Path_to_Template>
    ```

    如需使用 UE-V 和 Windows PowerShell 的詳細資訊，請參閱[使用 Windows PowerShell 和 WMI 管理 ue-v A.x 設定位置範本](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)。

-   透過**範本目錄路徑註冊範本**。 如果您使用設定範本目錄路徑來管理使用者電腦上的範本，請將 Office 2013 範本複製到 UE-V Agent 中定義的資料夾中。 下次範本自動更新（ApplySettingsCatalog.exe）排程的任務執行時，就會在裝置上註冊設定位置範本。 如需詳細資訊，請參閱[部署 ue-v 2 的設定範本目錄](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)。

-   透過**Configuration Manager 註冊範本**。 如果您使用 Configuration Manager 來管理 UE-V 設定的儲存範本，請重新建立範本基線 CAB，然後將其匯入 Configuration Manager，然後將比較基準部署到您的用戶端。 如需詳細資訊，請參閱適用于[Microsoft 使用者經驗 Virtualization 2 之 System Center 2012 Configuration Pack](https://go.microsoft.com/fwlink/?LinkId=317263)的檔中所提供的指導方針。






 

 





