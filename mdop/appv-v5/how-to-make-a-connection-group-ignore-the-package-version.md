---
title: 如何讓連線群組略過套件版本
description: 如何讓連線群組略過套件版本
author: dansimp
ms.assetid: 6ebc1bff-d190-4f4c-a6da-e09a4cca7874
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b64d1938419aef184c5df667bf71b8157de0450a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800474"
---
# 如何讓連線群組略過套件版本


Microsoft Application Virtualization （App-v） 5.0 SP3 可讓您將連接群組設定為使用任何版本的套件，這可簡化套件升級並減少您需要建立的連線群組數量。

若要在舊版 App-v 中升級套件，您必須執行數個步驟，包括停用連線群組及修改連線群組的 XML 定義檔案。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-V 5.0 SP3 的任務描述</th>
<th align="left">如何使用 App-v 5.0 SP3 執行任務</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>您可以將連線群組設定為接受任何版本的套件，這可讓您在不需停用連線群組的情況下升級套件。</p>
<p><strong>此功能的運作方式：</strong></p>
<ul>
<li><p>如果連線群組有權存取多個版本的套件，則會使用最新版本。</p></li>
<li><p>如果連線群組包含不正確版本的選用套件，則會忽略套件，而且不會封鎖連接群組的虛擬環境。</p></li>
<li><p>如果連接群組包含不正確版本的非選用套件，則無法建立連線群組的虛擬環境。</p></li>
</ul></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步驟</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server –管理主控台</p></td>
<td align="left"><ol>
<li><p>在管理主控台中，選取 [ <strong> 套件連線 </strong> &gt; <strong> 群組] </strong> 。</p></li>
<li><p>從連線群組程式庫中選取正確的連線群組。</p></li>
<li><p>按一下 <strong> </strong> [連線的套件] 窗格中的 [編輯]。</p></li>
<li><p>選取 <strong> </strong> 套件名稱旁邊的 [使用任何版本] 核取方塊，然後按一下 [套用] <strong> </strong> 。</p></li>
</ol>
<p>如需新增或升級套件的詳細資訊，請參閱 <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)"> 如何使用管理主控台新增或升級套件 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在獨立電腦上使用 app-v 用戶端</p></td>
<td align="left"><ol>
<li><p>建立連線群組 XML 檔。</p></li>
<li><p>若要升級套件，請將 [套件標籤 <strong> </strong> 屬性 VersionID] 設定 <strong> </strong> 為星號（ <strong>*</strong> ）。</p></li>
<li><p>使用下列 Cmdlet 來新增連線群組，並包含連線群組 XML 檔的路徑：</p>
<p><strong>附加 AppvClientConnectionGroup</strong></p></li>
<li><p>當您升級套件時，請使用下列 Cmdlet 來移除舊的套件、新增已升級的套件，併發布升級後的套件：</p>
<ul>
<li><p>RemoveAppvClientPackage</p></li>
<li><p>附加 AppvClientPackage</p></li>
<li><p>發佈-AppvClientPackage</p></li>
</ul></li>
</ol>
<p>如需詳細資訊，請參閱：</p>
<ul>
<li><p>此區段中的範例 XML 檔案（ <strong> 含選用套件的連線群組 XML 檔案 </strong> ）：如何在連線 <a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"> 群組中使用選用套件</a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</a></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 






## 相關主題


[管理連線群組](managing-connection-groups.md)

 

 





