---
title: 使用 App-V 部署 Microsoft Office 2010
description: 使用 App-V 部署 Microsoft Office 2010
author: dansimp
ms.assetid: ae0b0459-c0d6-4946-b62d-ff153f52d1fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90454373e9a1c894eba8cbf1b8642656b986bc94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800640"
---
# 使用 App-V 部署 Microsoft Office 2010


您可以使用下列其中一種方法，為 Microsoft 應用程式虛擬化（App-v）5.1 建立 Office 2010 套件：

-   應用程式虛擬化（App-v） Sequencer

-   應用程式虛擬化（App-v）套件加速器

## Office 2010 的 app-v 支援


下表顯示 App-V 版本、Office 套件建立的方法、支援的授權，以及 Office 2010 支援的部署。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支援的專案</th>
<th align="left">支援層級</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 App-v 版本</p></td>
<td align="left"><ul>
<li><p>4.6</p></li>
<li><p>5.0</p></li>
<li><p>5.1</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>建立套件</p></td>
<td align="left"><ul>
<li><p>序列</p></li>
<li><p>套件加速器</p></li>
<li><p>Office 部署套件</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>支援的授權</p></td>
<td align="left"><p>大量授權</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的部署</p></td>
<td align="left"><ul>
<li><p>桌面</p></li>
<li><p>個人 VDI</p></li>
<li><p>句</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## 使用排序器建立 Office 2010 App-V 5。1


排序 Office 2010 是在應用程式 V 5.1 上建立 Office 2010 套件的主要方法之一。 Microsoft 已透過知識庫文章提供詳細的食譜。 若要在 App-V 5.1 上建立 Office 2010 套件，請參閱下列連結，以取得詳細指示：

[如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## 使用套件加速器建立 Office 2010 App-V 5.1 套件


您可以透過套件加速器建立 Office 2010 App-V 5.1 套件。 Microsoft 已提供套件加速器，可在 Windows 10、Windows 8 和 Windows 7 上建立 Office 2010。 若要使用套件加速器在 App-v 上建立 Office 2010 套件，請參閱下列頁面，以存取適當的套件加速器：

-   [適用于 Office 專業增強版2010– Windows 8 的 app-v 5.0 套件加速器](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [適用于 Office 專業增強版2010的 app-v 5.0 套件加速器-Windows 7](https://go.microsoft.com/fwlink/p/?LinkId=330678)

如需如何使用 App-v 套件加速器建立虛擬應用程式套件的詳細指示，請參閱[如何使用 App-v 套件加速器建立虛擬應用程式套件](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)。

## 部署應用程式的 Microsoft Office 套件-V 5。1


您可以使用下列任何一種 App V 部署方法，部署 Office 2010 套件：

-   System Center Configuration Manager

-   App-v server

-   從 PowerShell 命令中獨立

## Office App-v 套件管理與自訂


您可以透過已知的套件管理機制，管理 Office 2010 套件，就像任何其他 App-V 5.1 套件一樣。 不需要任何特殊指示，例如新增、發佈、取消發佈或移除 Office 套件。

## Microsoft Office 與 Windows 整合


下表提供 Office 2010 支援整合點的完整清單。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">延伸點</th>
<th align="left">描述</th>
<th align="left">Office 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>適用于 Firefox 和 Chrome 的 Lync 會議加入外掛程式</p></td>
<td align="left"><p>使用者可以從 Firefox 和 Chrome 加入 Lync 會議</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>已傳送至 OneNote 列印驅動程式</p></td>
<td align="left"><p>使用者可以列印至 OneNote</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneNote 連結筆記</p></td>
<td align="left"><p>OneNote 連結筆記</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>傳送至 OneNote Internet Explorer 增益集</p></td>
<td align="left"><p>使用者可以從 IE 傳送至 OneNote</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Lync 和 Outlook 的防火牆例外狀況</p></td>
<td align="left"><p>Lync 和 Outlook 的防火牆例外狀況</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>MAPI 用戶端</p></td>
<td align="left"><p>原生應用程式和增益集可透過 MAPI 與虛擬 Outlook 互動</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Firefox 適用的 SharePoint 外掛程式</p></td>
<td align="left"><p>使用者可以在 Firefox 中使用 SharePoint 功能</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>[郵件] 控制台小程式</p></td>
<td align="left"><p>使用者在 Outlook 中取得 [郵件] 控制台小程式</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>主要 Interop 元件</p></td>
<td align="left"><p>支援受管理的增益集</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 檔快取處理常式</p></td>
<td align="left"><p>允許 Office 應用程式的檔快取</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Outlook 通訊協定搜尋處理常式</p></td>
<td align="left"><p>使用者可以在 outlook 中搜尋</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>Active X 控制項：</p></td>
<td align="left"><p>如需有關 ActiveX 控制項的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控制項 API 參考 </a> 。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Groove. SiteClient</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   PortalConnect.PersonalSite</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenDocuments</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   ExportDatabase</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SpreadSheetLauncher</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   StssyncHander</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   DragUploadCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   DragDownloadCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Sharpoint.OpenXMLDocuments</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   ClipboardCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   WinProj Activator</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   NameCtrl</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   STSUPld.CopyCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   CommunicatorMeetingJoinAx.JoinManager</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   LISTNET.Listnet</p></td>
<td align="left"><p>Active X 控制項</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   OneDrive 專業版瀏覽器協助程式</p></td>
<td align="left"><p>Active X 控制項]</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneDrive Pro 圖示重迭</p></td>
<td align="left"><p>當使用者查看資料夾 OneDrive Pro 資料夾時，Windows explorer shell 圖示會重迭</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## 其他資源


**Office 2013 App-V 封裝其他資源**

[將 Microsoft Office 部署為已排序的 App-v 套件所支援的案例](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**Office 2010 App-v 套件**

[Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序套件](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[建立或使用 App-v 5.0 Office 2010 套件時的已知問題](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**連線群組**

[在 Microsoft App 中部署連線群組-V v5](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[管理連線群組](managing-connection-groups51.md)

**動態設定**

[關於 App-V 5.1 動態組態](about-app-v-51-dynamic-configuration.md)






 

 





