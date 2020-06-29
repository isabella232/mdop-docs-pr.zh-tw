---
title: 如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝
description: 如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝
author: dansimp
ms.assetid: c3fd06f6-102f-43d1-a577-d5ced6ac537d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b454014da4e5f349af913d3fea8ea3837598a039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800463"
---
# 如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝


下列各節說明如何使用 PowerShell 在獨立用戶端電腦上執行各種管理工作：

-   [若要傳回套件清單](#bkmk-return-pkgs-standalone-posh)

-   [若要新增套件](#bkmk-add-pkgs-standalone-posh)

-   [發佈套件](#bkmk-pub-pkg-standalone-posh)

-   [將套件發佈至特定使用者](#bkmk-pub-pkg-a-user-standalone-posh)

-   [新增及發佈套件](#bkmk-add-pub-pkg-standalone-posh)

-   [取消發佈現有的套件](#bkmk-unpub-pkg-standalone-posh)

-   [針對特定使用者取消發佈套件](#bkmk-unpub-pkg-specfc-use)

-   [移除現有的套件](#bkmk-remove-pkg-standalone-posh)

-   [僅允許系統管理員發佈或取消發佈套件](#bkmk-admins-pub-pkgs)

-   [瞭解擱置的套件（UserPending 和 GlobalPending）](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a>若要傳回套件清單


使用下列資訊傳回有資格給特定使用者的套件清單：

**Cmdlet**： AppvClientPackage

**參數**：-Name-Version-PackageID-VersionID

**範例**： AppvClientPackage – Name "ContosoApplication"-版本2

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a>若要新增套件


使用下列資訊將套件新增到電腦。

**重要** 這個範例只會新增套件。 它不會將套件發佈至使用者或電腦。

 

**Cmdlet**： Add-AppvClientPackage

**範例**： $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a>發佈套件


使用下列資訊發佈已新增至特定使用者或全域至電腦上任何使用者的套件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">發佈方法</th>
<th align="left">Cmdlet 與範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>發佈至使用者</p></td>
<td align="left"><p><strong>Cmdlet </strong> ： Publish-AppvClientPackage</p>
<p><strong>範例 </strong> ： Publish-AppvClientPackage "ContosoApplication"</p></td>
</tr>
<tr class="even">
<td align="left"><p>全域發佈</p></td>
<td align="left"><p><strong>Cmdlet </strong> ： Publish-AppvClientPackage</p>
<p><strong>範例 </strong> ： Publish-AppvClientPackage "ContosoApplication"-全域</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a>將套件發佈至特定使用者


**記事** 您必須使用 App-v 5.0 SP2 修補程式套件5或更新版本，才能使用這個參數。

 

系統管理員可以將套件發佈至特定的使用者，方法是使用**publish-AppvClientPackage** Cmdlet 指定 Optional （ **UserSID** ）參數，其中 **-UserSID**代表使用者的安全性識別碼（SID）。

若要使用此參數：

-   您可以從使用者或系統管理員會話執行此 Cmdlet。

-   您必須以管理認證登入，才能使用此參數。

-   最終使用者必須登入。

-   您必須提供最終使用者的安全識別碼（SID）。

**Cmdlet**： Publish-AppvClientPackage

**範例**： Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a>新增及發佈套件


使用下列資訊將套件新增到電腦，並將其發佈給使用者。

**Cmdlet**： Add-AppvClientPackage

**範例**： Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |發佈-AppvClientPackage

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a>取消發佈現有的套件


使用下列資訊來取消發佈已有資格給使用者但無法從電腦移除套件的套件。

**Cmdlet**：取消發佈-AppvClientPackage

**範例**：取消發佈-AppvClientPackage "ContosoApplication"

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a>針對特定使用者取消發佈套件


**記事** 您必須使用 App-v 5.0 SP2 修補程式套件5或更新版本，才能使用這個參數。

 

系統管理員可以使用選擇性的 **– UserSID**參數和**AppvClientPackage** Cmdlet 來取消發佈特定使用者的套件，其中 **-UserSID**代表使用者的安全性識別碼（SID）。

若要使用此參數：

-   您可以從使用者或系統管理員會話執行此 Cmdlet。

-   您必須以管理認證登入，才能使用此參數。

-   最終使用者必須登入。

-   您必須提供最終使用者的安全識別碼（SID）。

**Cmdlet**：取消發佈-AppvClientPackage

**範例**：取消發佈-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a>移除現有的套件


使用下列資訊從電腦中移除套件。

**Cmdlet**： Remove-AppvClientPackage

**範例**： Remove-AppvClientPackage "ContosoApplication"

**記事** 出於明確起見，前幾個範例的 App-V Cmdlet 已指派給變數;不需要作業。 大多數的 Cmdlet 可以結合顯示在中，[以新增及發佈套件](#bkmk-add-pub-pkg-standalone-posh)。 如需詳細教學課程，請參閱[app-v 5.0 Client PowerShell 深入探索](https://go.microsoft.com/fwlink/?LinkId=324466)。

 

## <a href="" id="bkmk-admins-pub-pkgs"></a>僅允許系統管理員發佈或取消發佈套件


**記事** 
**從 app-v 5.0 SP3 開始，支援這項功能。**

 

使用下列 Cmdlet 和參數，僅允許系統管理員（而非最終使用者）發佈或取消發佈套件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Cmdlet</strong></p></td>
<td align="left"><p>Set-AppvClientConfiguration</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>參數</strong></p></td>
<td align="left"><p>-RequirePublishAsAdmin</p>
<p>參數值：</p>
<ul>
<li><p>0-False</p></li>
<li><p>1-True</p></li>
</ul>
<p><strong>範例： </strong> ： Set-AppvClientConfiguration – RequirePublishAsAdmin1</p></td>
</tr>
</tbody>
</table>

 

若要使用應用程式 V 管理主控台來設定此設定，請參閱[如何使用管理主控台發佈套件](how-to-publish-a-package-by-using-the-management-console-51.md)。

## <a href="" id="bkmk-understd-pend-pkgs"></a>瞭解擱置的套件（UserPending 和 GlobalPending）


**從 app-v 5.0 SP2 開始**：如果您執行的 PowerShell Cmdlet 會影響目前正在使用的套件，您嘗試執行的工作會放在擱置中的狀態。 例如，如果您嘗試在使用該套件中的應用程式時發佈套件，然後執行**AppvClientPackage**，則會在 Cmdlet 輸出中顯示擱置狀態，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Cmdlet 輸出專案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>UserPending</p></td>
<td align="left"><p>指出列出的套件是否有正在套用至使用者的待執行工作：</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalPending</p></td>
<td align="left"><p>指出列出的套件是否有全域套用到電腦的未決工作：</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

根據下列規則，待定的工作將會在稍後執行：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務類型</th>
<th align="left">適用的規則</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以使用者為基礎的工作，例如，將套件發佈給使用者</p></td>
<td align="left"><p>暫停的工作將會在使用者登出後執行，然後重新登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>以全域為基礎的工作，例如，全域啟用連接群組</p></td>
<td align="left"><p>當電腦關閉後再重新開機時，會執行待處理的工作。</p></td>
</tr>
</tbody>
</table>

 

如需未決工作的詳細資訊，請參閱[關於 App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)。

您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)

 

 





