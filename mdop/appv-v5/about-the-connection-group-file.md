---
title: 關於連線群組檔案
description: 關於連線群組檔案
author: dansimp
ms.assetid: bfeb6013-a7ca-4e36-9fe3-229702e83f0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5e5cb93326ce182d71de0f0f89cc569823d6154e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800717"
---
# 關於連線群組檔案


**本主題內容如下：**

-   [連線群組檔案用途和位置](#bkmk-cg-purpose-loc)

-   [連線群組 XML 檔案的結構](#bkmk-define-cg-5-0sp3)

-   [在連線群組中設定套件的優先順序](#bkmk-config-pkg-priority-incg)

-   [支援的虛擬應用程式連線設定](#bkmk-va-conn-configs)

## <a href="" id="bkmk-cg-purpose-loc"></a>連線群組檔案用途和位置


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>連線群組用途</p></td>
<td align="left"><p>連線群組是一個 App-v 功能，可讓您將套件組成群組，以建立虛擬環境，讓這些套件中的應用程式可以彼此互動。</p>
<p>範例：您想要在 Microsoft Office 中使用外掛程式。 您可以建立包含外掛程式的套件，並建立包含 Office 的另一個套件，然後將這兩個套件新增到連線群組，以讓 Office 使用這些外掛程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>連線群組檔案的運作方式</p></td>
<td align="left"><p>當您套用 Application Virtualization 5.0 連線群組檔案時，會在執行時間將在檔案中列舉的套件合併成單一虛擬環境。 使用 Microsoft Application Virtualization （App-v）5.0 連線群組檔案來設定現有的 Application Virtualization 5.0 連線群組。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>範例檔路徑</p></td>
<td align="left"><p>%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups {6CCC7575-162E-4152-9407-ED411DA138F4} {4D1E16E1-8EF8-41ED-92D5-8910A8527F96}。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-define-cg-5-0sp3"></a>連線群組 XML 檔案的結構


**本節內容：**

-   [定義連接群組的參數](#bkmk-params-define-cg)

-   [在連線群組中定義套件的參數](#bkmk-params-define-pkgs-incg)

-   [App-V 5.0 SP3 範例連線群組 XML 檔案](#bkmk-50sp3-exp-cg-xml)

-   [App-v 5.0 透過 App-V 5.0 SP2 範例連線群組 XML 檔案](#bkmk-50thru50sp2-exp-cg-xm)

### <a href="" id="bkmk-params-define-cg"></a>定義連接群組的參數

下表說明 XML 檔案中定義連線群組本身（而非套件）的參數。

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
<td align="left"><p>架構名稱</p></td>
<td align="left"><p>架構的名稱。</p>
<p><strong>適用于 App-v 5.0 SP3 </strong> ：如果您想要使用此表格中所述的新 [選用套件] 和「使用任何版本」功能，您必須在 XML 檔案中指定下列架構：</p>
<p><code>xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>AppConnectionGroupId</p></td>
<td align="left"><p>這個連線群組的唯一 GUID 識別碼。 連線群組狀態與此識別碼相關聯。 只有在建立連線群組時，才能指定此識別碼。</p>
<p>您可以輸入以下內容來建立新的 GUID： <strong>[Guid]::NewGuid()</strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VersionId</p></td>
<td align="left"><p>此版本的連線群組的版本 GUID 識別碼。</p>
<p>當您更新連線群組時（例如，新增或更新新的套件），您必須更新版本 GUID 以反映新版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DisplayName</p></td>
<td align="left"><p>[連線] 群組的 [顯示名稱]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>優先順序</p></td>
<td align="left"><p>[連接] 群組的 [選用優先順序] 欄位。</p>
<p><strong>"0" </strong> - 表示最高優先順序。</p>
<p>如果需要優先順序，但尚未進行設定，則由於無法決定要使用的正確連線群組，套件將會失敗。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-params-define-pkgs-incg"></a>在連線群組中定義套件的參數

在連線 &lt; 群組 XML 檔案的 [套件] &gt; 區段中，您可以指定每個套件的唯一套件識別碼與版本識別碼，以列出連接群組中的成員套件，如下表所述。 清單中的第一個套件具有最高優先順序。

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
<td align="left"><p>PackageId</p></td>
<td align="left"><p>此套件的唯一 GUID 識別碼。 發佈更新版本的套件時，此 GUID 不會變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>VersionId</p></td>
<td align="left"><p>套件版本的唯一 GUID 識別碼。</p>
<p><strong>適用于 App-v 5.0 SP3 </strong> ：如果您指定 [ <strong> *] </strong> 做為套件版本，則會動態插入最新可用套件版本的 GUID。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IsOptional</p></td>
<td align="left"><p><strong>適用于 App-V 5.0 SP3 </strong> ：參數，可讓您在連線群組中將套件設為選用。 有效的專案為：</p>
<ul>
<li><p><strong>"true" </strong> – [連線] 群組中的 [套件] 是選擇性的</p></li>
<li><p><strong>"false" </strong> –在連線群組中需要套件</p></li>
</ul>
<p>瞭解 <a href="how-to-use-optional-packages-in-connection-groups.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md)"> 如何在連線群組中使用選用套件 </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-50sp3-exp-cg-xml"></a>App-V 5.0 SP3 範例連線群組 XML 檔案

下列範例連線群組 XML 檔案會顯示先前表格中的欄位範例，並醒目提示 App-V 5.0 SP3 的新專案。

```XML
<?xml version="1.0" encoding="UTF-16"?>
<appv:AppConnectionGroup 
   xmlns="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
   xmlns:appv="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
   AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
   VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"  
   Priority="0"  
   DisplayName="Sample Connection Group">
   <appv:Packages>
      <appv:Package      
         PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
         VersionId="*"
         IsOptional=”true”
      />    
     <appv:Package
        PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
        VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
        IsOptional="false"
     />  
   </appv:Packages>
</appv:AppConnectionGroup>
```

### <a href="" id="bkmk-50thru50sp2-exp-cg-xm"></a>App-v 5.0 透過 App-V 5.0 SP2 範例連線群組 XML 檔案

下列範例連線群組 XML 檔案是透過 App-V 5.0 SP2 套用至 App-v 5.0。 它會顯示上表中的欄位範例，但不會排除上述 App-v 5.0 SP3 所述的變更。

```XML
<?xml version="1.0" encoding="UTF-16"?>
<appv:AppConnectionGroup
   xmlns="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
   xmlns:appv="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
   AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
   VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
   Priority="0"
   DisplayName="Sample Connection Group">
   <appv:Packages>
      <appv:Package``      
         PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
         VersionId="C7DF4F63-5288-439C-ACEF-EF06BF401EC5"
      />
      <appv:Package
         PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
         VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
      />
   </appv:Packages>
</appv:AppConnectionGroup
 ```

## <a href="" id="bkmk-config-pkg-priority-incg"></a>在連線群組中設定套件的優先順序


封裝優先順序是使用套件清單順序設定。 檔中的第一個套件具有最高優先順序。 清單中的後續套件具有遞減優先順序。

封裝優先順序是在虛擬環境初始化期間因應避免的資源碰撞問題的解決方法。 例如，如果在同一個虛擬環境中開啟的兩個套件定義相同的登錄 DWORD 值，則具有最高優先順序的套件會決定所設定的值。

您可以使用下列方法，使用連線群組檔案來設定每個連接群組：

-   指定連線群組的執行時間優先順序。

    **記事** 只有當套件與一個以上的連線群組相關聯時，才需要優先順序。

     

-   在連線群組中指定套件優先順序。

如果正在執行的虛擬應用程式是從原生應用程式要求（例如，Microsoft Windows Explorer）啟動時，[優先順序] 欄位是必要的。 App-v 用戶端會使用優先順序來判斷應用程式應該在哪個連線群組虛擬環境中執行。 如果虛擬應用程式是多個連線群組的一部分，就會發生這種情況。

如果虛擬應用程式是使用另一個虛擬應用程式開啟，則會使用原始虛擬應用程式的虛擬環境。 在這種情況下，不會使用 [優先順序] 欄位。

**範例：**

Microsoft Outlook 正在虛擬環境**XYZ**中執行的虛擬應用程式。 當您開啟附加的 Microsoft Word 檔時，無論虛擬化 Microsoft Word 的關聯連線群組或執行時間優先順序為何，在虛擬環境**XYZ**中都會開啟虛擬化版本 microsoft word。

## <a href="" id="bkmk-va-conn-configs"></a>支援的虛擬應用程式連線設定


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定</th>
<th align="left">範例案例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將. exe 檔案和外掛程式（.dll）</p></td>
<td align="left"><ul>
<li><p>您想要將 Microsoft Office 發佈給所有使用者，但只將 Microsoft Excel 外掛程式發佈至使用者的子集。</p></li>
<li><p>針對適當的使用者啟用 [連接] 群組。</p></li>
<li><p>根據需要逐一更新每個套件。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>將. exe 檔案和中介軟體應用程式</p></td>
<td align="left"><ul>
<li><p>您的應用程式需要一個中介軟體應用程式，或多個應用程式，它們都依賴同一個中介軟體執行時間版本。</p></li>
<li><p>所有需要一或多個應用程式的電腦會透過應用程式和中介軟體應用程式執行時間來接收連接群組。</p></li>
<li><p>您可以選擇性地將多個中介軟體應用程式合併成單一連線群組。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">範例</th>
<th align="left">範例描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>財務部門的虛擬應用程式連線群組</p></td>
<td align="left"><ul>
<li><p>中介軟體應用程式1</p></li>
<li><p>中介軟體應用程式2</p></li>
<li><p>中介軟體應用程式3</p></li>
<li><p>中介軟體應用程式執行時間</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>人力資源部門的虛擬應用程式連線群組</p></td>
<td align="left"><ul>
<li><p>中介軟體應用程式5</p></li>
<li><p>中介軟體應用程式6</p></li>
<li><p>中介軟體應用程式執行時間</p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>將. exe 檔和 .exe 檔案</p></td>
<td align="left"><p>您有一個依賴另一個應用程式的應用程式，而您想要將套件保持在運作效率、授許可權制或推出時間範圍之外。</p>
<p><strong>範例：</strong></p>
<p>如果您要部署 Microsoft Lync 2010，您可以使用三個套件：</p>
<ul>
<li><p>Microsoft Office2010</p></li>
<li><p>Microsoft Communicator2007</p></li>
<li><p>Microsoft Lync2010</p></li>
</ul>
<p>您可以使用下列連線群組來管理部署：</p>
<ul>
<li><p>Microsoft Office2010 和 Microsoft Communicator2007</p></li>
<li><p>Microsoft Office2010 和 Microsoft Lync2010</p></li>
</ul>
<p>部署完成後，您可以建立單一的 Microsoft Office2010 + Microsoft Lync2010 套件，或保留並維護它們為個別套件，然後使用連線群組進行部署。</p></td>
</tr>
</tbody>
</table>

 






## 相關主題


[管理連線群組](managing-connection-groups.md)

 

 





