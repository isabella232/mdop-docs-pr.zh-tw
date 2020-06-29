---
title: 如何在連線群組中使用選用套件
description: 如何在連線群組中使用選用套件
author: dansimp
ms.assetid: 4d08a81b-55e5-471a-91dc-9a684fb3c9a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 64a2c0758294bfa617d3d85f888cfce3a2c0d21e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800392"
---
# 如何在連線群組中使用選用套件


從 Microsoft Application Virtualization （App-v） 5.0 SP3 中開始，您可以在連線群組中新增選用套件，以簡化連接群組管理。 下表摘要列出您可以使用選用套件輕鬆完成的工作，並提供每個任務的相關指示連結。

**記事** 
**只有在 app-v 5.0 SP3 中才支援選用套件。**

 

使用選用的套件之前，請參閱[在連線群組中使用選用套件的需求](#bkmk-reqs-using-cg)。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">連結至指示</th>
<th align="left">工作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)">針對有不同套件的多個使用者使用一個連線群組（含選用套件）</a></p></td>
<td align="left"><p>使用單一連線群組讓不同的應用程式和外掛程式可供不同的使用者使用。</p>
<p>例如，您想要將 Microsoft Office 發佈給所有的最終使用者，但將不同的外掛程式發佈到不同的使用者子集。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)">取消發佈或刪除選用的套件，或取消發佈選用的套件，稍後再重新發佈，而不需變更連接群組</a></p></td>
<td align="left"><p>取消發佈、刪除或重新發佈選用的套件，而不需要停用、移除、編輯、新增及重新啟用 App-v 用戶端上的連線群組。</p>
<p>您也可以取消發佈選用的套件，稍後再重新發佈，而不需要停用或重新發佈連線群組。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a>將一個連接群組與選用的套件搭配使用，可供多位使用者使用不同套件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務描述</th>
<th align="left">如何執行任務</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>應用程式-V 5.0 SP3</strong></p>
<p>您可以在連線群組中新增選擇性套件，這可讓您提供不同的應用程式和外掛程式組合給不同的使用者。</p>
<p><strong>範例 </strong> ：您想要將 Microsoft Office 發佈給您的使用者，但只為使用者子集啟用特定外掛程式。</p>
<p>若要這樣做，請建立包含 Office 套件的連線群組，以及另一個隨附 Office 外掛程式的套件，然後將外掛程式封裝為選用。</p>
<p>不具備外掛程式套件資格的使用者仍然可以執行 Office。</p></td>
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
<li><p>在管理主控台中，選取 [ <strong> 套件] </strong> 以開啟 [套件] 頁面。</p></li>
<li><p>選取 [連線 <strong> 群組] </strong> 以顯示 [連線群組] 程式庫。</p></li>
<li><p>從連線群組程式庫中選取正確的連線群組。</p></li>
<li><p>按一下 <strong> </strong> [連線的套件] 窗格中的 [編輯]。</p></li>
<li><p>選取 <strong> </strong> 套件名稱旁的 [選擇性]。</p></li>
<li><p>選取 [ <strong> 新增套件對群組的存取權] </strong> 核取方塊。 此必要步驟會將您在指派套件至 Active Directory 群組時所設定的套件權利新增至 [連線] 群組。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Server-PowerShell Cmdlet</p></td>
<td align="left"><p>使用下列 Cmdlet，並指定 <strong> -Optional </strong> 參數：</p>
<p><strong>附加 AppvServerConnectionGroupPackage</strong></p>
<p><strong>句法</strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong>範例：</strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在獨立電腦上使用 app-v 用戶端</p></td>
<td align="left"><ol>
<li><p>建立連線群組 XML 檔，並將套件卷 <strong> 標 </strong> 屬性 <strong> IsOptional 設定 </strong> 為 <strong> "true"。</strong></p></li>
<li><p>使用下列 Cmdlet 來新增和啟用 [連線] 群組：</p>
<ul>
<li><p>附加 AppvClientConnectionGroup</p></li>
<li><p>Enable-AppvClientConnectionGroup</p></li>
</ul></li>
</ol>
<p><strong>含選用套件的連線群組 XML 檔範例：</strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用 app-v 5.0 SP3 之前的版本</strong></p></td>
<td align="left"><p>您必須建立許多連線群組，才能讓特定的使用者使用特定的應用程式和外掛程式組合。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a>取消發佈或刪除選用的套件，或取消發佈選用的套件，稍後再重新發佈，而不需變更連接群組


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務描述</th>
<th align="left">如何執行任務</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>應用程式-V 5.0 SP3</strong></p>
<p>您可以取消發佈、刪除或重新發佈位於連線群組中的選擇性套件，而不需要停用或重新啟用 App-v 用戶端的連線群組。</p>
<p>您也可以取消發佈選用的套件，稍後再重新發佈，而不需要停用或重新發佈連線群組。</p>
<p><strong>範例 </strong> ：如果您發佈的是包含 Microsoft Office 外掛程式的選用套件，而您想要移除該外掛程式，您可以取消發佈套件，而不需要停用連線群組。</p></td>
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
<td align="left"><ul>
<li><p>若要取消發佈套件：請在管理主控台中，選取 [選擇 <strong> 套件] </strong> 頁面，以滑鼠右鍵按一下您要取消發佈的套件，然後按一下 [ <strong> 取消發佈] </strong> 。</p></li>
<li><p>若要從連線群組中移除選用套件：請在 [連線 <strong> 群組 </strong> ] 頁面上，選取您要移除的套件，然後按一下向右箭號，從左下角的 [連線] 群組窗格中移除套件。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在獨立電腦上使用 app-v 用戶端</p></td>
<td align="left"><p>使用下列現有的 Cmdlet：</p>
<ul>
<li><p>取消發佈-AppvClientPackage</p></li>
<li><p>移除-AppvClientPackage</p></li>
</ul>
<p>如需詳細資訊，請參閱 <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> 如何使用 PowerShell 管理在獨立電腦上執行的 app-v 5.0 套件 </a> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用 app-v 5.0 SP3 之前的版本</strong></p></td>
<td align="left"><p>您必須：</p>
<ol>
<li><p>從每個啟用的 App-v 用戶端電腦中移除連線群組。</p></li>
<li><p>取消發佈套件。</p></li>
<li><p>從連線群組的定義中移除套件。</p></li>
<li><p>重新發佈連線群組。</p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a>在連線群組中使用選用套件的需求


在連接群組中使用選用套件之前，請先檢查下列需求：

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
<td align="left"><p>[連線群組] 必須至少包含一個非選用的套件。</p></td>
<td align="left"><ul>
<li><p>請仔細檢查您是否符合這個需求，因為 App-v Server 和 PowerShell Cmdlet 不會驗證是否已滿足需求。</p></li>
<li><p>如果您不小心建立一個不包含至少一個非選用套件的連線群組，而使用者嘗試在該連線群組中開啟封裝的應用程式，則連接群組會失敗。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p>使用者發佈的連線群組可以包含全域發佈或使用者的套件。</p></li>
<li><p>全域發佈的連線群組必須只包含全域發佈的套件。</p></li>
</ul></td>
<td align="left"><p>[全域發佈的連線群組] 必須包含全域發行的套件，以確保啟動連線群組的虛擬環境時，套件可供使用。</p>
<p>如果您嘗試新增或啟用全域發佈的連線群組（包含使用者發佈的套件），連線群組將會失敗。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>發佈包含這些套件的連線群組之前，您必須發佈所有非選用套件。</p></td>
<td align="left"><p>如果沒有任何非選用的套件，則無法啟動連線群組的虛擬環境。</p>
<p>如果沒有發佈任何非選用套件，App-v 用戶端將無法新增或啟用連接群組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在您取消發佈全域發佈的套件之前，請確定擁有該電腦上所有使用者的 [連線群組] 不再需要套件。</p></td>
<td align="left"><p>系統不會檢查套件是否為其他使用者的連線群組的一部分。 取消發佈全域套件將使該電腦上的每個使用者都無法使用它，因此請確定每個使用者的連線群組已不包含套件，或者將套件設為選用。</p></td>
</tr>
</tbody>
</table>

 






## 相關主題


[管理連線群組](managing-connection-groups.md)

 

 





