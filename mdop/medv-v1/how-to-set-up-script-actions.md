---
title: 如何設定指令碼動作
description: 如何設定指令碼動作
author: dansimp
ms.assetid: 367e28f1-d8c2-4845-a01b-2fff9128ccfd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bfa264be447a0a8560e4af16ccaadc2ec1db3f6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800081"
---
# 如何設定指令碼動作


[腳本操作編輯器] 可讓系統管理員建立在 MED-V 工作區設定期間要執行的動作，以及定義其執行順序。

以下是可新增至網域設定腳本的動作清單：

-   **重新開機 windows**-重新開機 windows。

-   **加入網域**-如果加入網域，請加入此動作並設定使用者名稱、密碼、完全限定功能變數名稱、NetBIOS 功能變數名稱及組織單位（選用）。

-   **檢查連線性**-設定要連線的伺服器，並確認 med-v 工作區可以連線到網路資源（例如網域伺服器）。

-   **命令列**-在 med-v 工作區中設定腳本，然後輸入包含腳本路徑及腳本引數的命令列。

-   [**重新命名電腦**]：根據已定義的設定重新命名虛擬電腦電腦。

-   **停用自動登**入：停用 Windows 自動登入。 在將電腦新增至網域的腳本結尾，應該新增此動作。

## <a href="" id="how-to-set-up-script-actions-"></a>如何設定指令碼動作


**設定腳本動作**

1.  在 [ **VM 設定**] 索引標籤上，按一下 [**腳本編輯器**]。

2.  在 [**腳本動作**] 對話方塊中，按一下 [**新增**]，然後在子功能表上，按一下所要的動作。

3.  如下表所述設定動作。

    **記事** 
    [ **VM 設定**] 索引標籤中的 [**重新命名電腦**] 已設定。如需詳細資訊，請參閱[如何設定 VM 電腦名稱稱模式屬性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。

     

~~~
**Note**  
To rename a computer, Windows must be restarted. It is recommended to add a Restart Windows action following a Rename Computer action.
~~~



4. 選取動作，然後按一下 [**向上**] 或 [**向下**] 來設定動作順序。

5. 按一下 **\[確定\]**。

**注意**  
執行 Join 網域腳本時，若要讓腳本正常運作，登入 MED-V 工作區虛擬機器的使用者必須擁有本機系統管理員許可權。



**注意**  
在執行停用自動登入腳本時，建議您在初始設定完成後停用用於自動登入的本機來賓帳戶。



### <a href="" id="bkmk-joindomainproperties"></a>

**加入網域屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將 VM 加入網域時要使用的認證</p></td>
<td align="left"><p>將 VM 加入網域時，請選取下列其中一個認證：</p>
<ul>
<li><p><strong>使用 MED-V 認證 </strong> -最終使用者認證。</p></li>
<li><p><strong>使用下列認證 </strong> —指定的認證; 在對應的欄位中輸入使用者名稱和密碼。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>所有的 MED-V 工作區使用者都能看到您輸入的認證。 建議您不要提供網域管理員認證。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>要加入的網域</p></td>
<td align="left"><p>選取下列其中一項：</p>
<ul>
<li><p><strong>在啟動工作區時使用功能變數名稱 </strong> ，即在登入 med-v 用戶端時加入由最終使用者輸入的網域。</p>
<p>若要定義從 NetBIOS 到完全限定功能變數名稱的對應，請按一下 [ <strong> 全域網域對應表] </strong> 。 在 [全域網域對應表] 中，按一下 [ <strong> 新增] </strong> ，輸入 <strong> NetBIOS 功能變數名稱 </strong> 及 <strong> 完整的功能變數名稱 </strong> ，然後按一下 <strong> [確定] </strong> 。</p></li>
<li><p><strong>使用下列功能變數名稱 </strong> —加入指定的網域; 在對應的欄位中輸入功能變數名稱和 NetBIOS 功能變數名稱。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>組織單位</p></td>
<td align="left"><p>您可以指定組織單位（OU），將電腦加入特定的 OU。 格式必須遵循 OU 辨識名稱： OU = &lt; 組織單位 &gt; 、 &lt; 網網域控制站 &gt; （例如，OU = QATest、DC = IL、DC = med-v、dc = com）。</p>
<div class="alert">
<strong>警告</strong><br/><p>僅支援單一階層 OU，如上述範例所示。</p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-checkconnectivityproperties"></a>

**檢查連通性屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IP 位址</p></td>
<td align="left"><p>您要驗證連線之伺服器的 IP 位址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>連接埠</p></td>
<td align="left"><p>您要驗證連線之伺服器的埠。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>逾時</p></td>
<td align="left"><p>超時前等候回應的秒數。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-commandlineproperties"></a>

**命令列屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>路徑</p></td>
<td align="left"><p>命令列的路徑。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Arguments</p></td>
<td align="left"><p>命令列引數。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>等待退出</p></td>
<td align="left"><p>選取核取方塊以等待傳回，然後繼續執行腳本動作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>失敗的錯誤</p></td>
<td align="left"><p>如果返回的值不是指定的值，請選取此核取方塊。</p>
<p>輸入會將命令指示為成功的值。</p>
<p>預設值： <strong> 0</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>只執行一次</p></td>
<td align="left"><p>選取此核取方塊，只執行命令列一次。 如果腳本失敗或已取消，就不會再執行此命令。</p></td>
</tr>
<tr class="even">
<td align="left"><p>這個命令列會在工作區中重新開機 Windows</p></td>
<td align="left"><p>如果命令列在完成後導致重新開機，請選取此核取方塊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允許互動</p></td>
<td align="left"><p>如果命令需要使用者互動，請選取此核取方塊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>進度訊息</p></td>
<td align="left"><p>在執行命令時要顯示給使用者的訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>失敗訊息</p></td>
<td align="left"><p>如果命令失敗，要向使用者顯示的訊息。</p></td>
</tr>
</tbody>
</table>

 

設定命令列動作時，可以按照下表中的定義來使用幾個變數。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>%MEDVUser%</p></td>
<td align="left"><p>已驗證的使用者名稱。</p></td>
<td align="left"><p>MED-V 驗證的使用者名稱。 您可以在加入網域 VM 設定腳本中使用使用者名稱和密碼。</p></td>
</tr>
<tr class="even">
<td align="left"><p>%MEDVPassword%</p></td>
<td align="left"><p>已驗證的密碼。</p></td>
<td align="left"><p>MED-V 驗證密碼。 您可以在加入網域 VM 設定腳本中使用使用者名稱和密碼。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>%MEDVDomain%</p></td>
<td align="left"><p>已設定網域。</p></td>
<td align="left"><p>在 MED-V 驗證中設定的網域。 它可以在 VM 設定腳本上使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>%DesiredMachineName%</p></td>
<td align="left"><p>[電腦名稱稱]。</p></td>
<td align="left"><p>管理應用程式中設定的唯一電腦名稱稱。 您可以在 VM 設定腳本中使用它。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[如何設定 MED-V 工作區的虛擬機器設定](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[如何設定 VM 電腦名稱模式內容](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

 

 





