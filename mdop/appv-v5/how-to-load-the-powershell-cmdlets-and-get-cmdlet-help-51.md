---
title: 如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明
description: 如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明
author: dansimp
ms.assetid: b6ae5460-2c3a-4030-b132-394d9d5a541e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 32b5bb26331f204acffbf96ea119ac4209c3cd89
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800471"
---
# 如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明


本主題涵蓋的內容：

-   [使用 PowerShell Cmdlet 的需求](#bkmk-reqs-using-posh)

-   [載入 PowerShell Cmdlet](#bkmk-load-cmdlets)

-   [取得 PowerShell Cmdlet 的說明](#bkmk-get-cmdlet-help)

-   [顯示 PowerShell Cmdlet 的說明](#bkmk-display-help-cmdlet)

## <a href="" id="bkmk-reqs-using-posh"></a>使用 PowerShell Cmdlet 的需求


請參閱下列使用 App-v PowerShell Cmdlet 的需求：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">需求</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>只有當您使用下列其中一種方法，才能執行 App-v Server Cmdlet 的授權：</p></td>
<td align="left"><ul>
<li><p><strong>當您部署並設定 App-v Server 時 </strong> ：</p>
<p>指定擁有管理 App V 環境許可權的 Active Directory 群組或個別使用者。 瞭解 <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"> 如何部署 app-v 5.1 伺服器 </a> 。</p></li>
<li><p><strong>在您部署 App-v Server 後 </strong> ：</p>
<p>使用 App-v 管理主控台新增其他 Active Directory 群組或使用者。 瞭解 <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console51.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)"> 如何使用管理主控台新增或移除系統管理員 </a> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>需要提升許可權的命令提示字元的 Cmdlet</p></td>
<td align="left"><ul>
<li><p>附加 AppvClientPackage</p></li>
<li><p>移除-AppvClientPackage</p></li>
<li><p>Set-AppvClientConfiguration</p></li>
<li><p>附加 AppvClientConnectionGroup</p></li>
<li><p>移除-AppvClientConnectionGroup</p></li>
<li><p>附加 AppvPublishingServer</p></li>
<li><p>移除-AppvPublishingServer</p></li>
<li><p>傳送 AppvClientReport</p></li>
<li><p>Set-AppvClientMode</p></li>
<li><p>Set-AppvClientPackage</p></li>
<li><p>Set-AppvPublishingServer</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>最終使用者可以執行的 Cmdlet，除非您將其設定為需要提升的命令提示字元</p></td>
<td align="left"><ul>
<li><p>發佈-AppvClientPackage</p></li>
<li><p>取消發佈-AppvClientPackage</p></li>
</ul>
<p>若要將這些 Cmdlet 設定為需要提升許可權的命令提示字元，請使用下列其中一種方法：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">更多資源</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong> </strong> 使用 <strong> -RequirePublishAsAdmin 參數執行 AppvClientConfiguration Cmdlet </strong> 。</p></td>
<td align="left"><ul>
<li><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md#bkmk-admin-only-posh-topic-cg)">如何使用 PowerShell 來管理獨立電腦上的連線群組</a></p></li>
<li><p><a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>針對應用程式 V 用戶端啟用 [需要以系統管理員身分發布] 群組原則設定。</p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-51.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md)">如何使用 Management Console 發佈套件</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-load-cmdlets"></a>載入 PowerShell Cmdlet

載入 PowerShell Cmdlet 模組：

1.  開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。

2.  輸入下列其中一個命令來載入您想要的模組的 Cmdlet：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 元件</th>
<th align="left">輸入的命令</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server</p></td>
<td align="left"><p>匯入-模組 AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>匯入-模組 AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 用戶端</p></td>
<td align="left"><p>匯入-模組 AppvClient</p></td>
</tr>
</tbody>
</table>

## <a href="" id="bkmk-get-cmdlet-help"></a>取得 PowerShell Cmdlet 的說明
從 App-v 5.0 SP3 開始，以下兩種格式可提供 Cmdlet 說明：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">格式</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以可下載的模組</p></td>
<td align="left"><p>下載 Cmdlet 模組後，請下載最新的協助：</p>
<ol>
<li><p>開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</p></li>
<li><p>輸入下列其中一個命令來載入您想要的模組的 Cmdlet：</p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 元件</th>
<th align="left">輸入的命令</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server</p></td>
<td align="left"><p>更新-協助-模組 AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>更新-協助-模組 AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 用戶端</p></td>
<td align="left"><p>更新-協助-模組 AppvClient</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上為網頁</p></td>
<td align="left"><p>請參閱 Microsoft 桌上出版 [優化套件自動化] 下的 app-v 節點， <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> 以使用 Windows PowerShell </a> 。</p></td>
</tr>
</tbody>
</table>

## <a href="" id="bkmk-display-help-cmdlet"></a>顯示 PowerShell Cmdlet 的說明
若要顯示特定 PowerShell Cmdlet 的說明：

1.  開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。

2.  輸入**get-help** &lt; *Cmdlet* &gt; ，例如， **get-help AppvClientPackage**。

您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

 

 





