---
title: 如何設定已發佈的應用程式
description: 如何設定已發佈的應用程式
author: dansimp
ms.assetid: 43a59ff7-5d4e-49dc-84e5-1082bc4dd8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cb5736382f03e818ef10aa814a8e61044ca2b73a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810479"
---
# 如何設定已發佈的應用程式


與主機作業系統不相容的應用程式，可以在 MED-V 工作區中執行，並以與從桌面開始的方式從 MED-V 中開始，從 [開始] 功能表或從本機主機快捷方式開始。 已選取並定義的應用程式稱為發佈的應用程式。 本節中的程式說明如何新增和移除已發佈的應用程式。

您可以使用下列其中一種方式發佈應用程式：

-   做為應用程式：在應用程式的命令列中輸入，以選取特定的應用程式。 只會發佈選取的應用程式。

-   [作為功能表]：選取包含多個應用程式的資料夾。 該資料夾中的所有應用程式都會發佈並顯示為功能表。

## <a href="" id="bkmk-addingapublishedapplication"></a>如何將已發佈的應用程式新增至 MED-V 工作區


**將應用程式新增至 MED-V 工作區**

1.  按一下要設定的 MED-V 工作區。

2.  在 [**應用程式**] 窗格的 [**已發佈的應用程式**] 區段中，按一下 [**新增**] 以新增應用程式。

3.  按照下表所述設定應用程式的屬性。

4.  在 [**原則**] 功能表上，選取 [**確認**]。

    **注意**  
    如果您將 Internet Explorer 設為已發佈的應用程式，以確保 Web 重新導向正常運作，請確定任何參數都不在括弧中。



**已發佈的應用程式屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>啟用</p></td>
<td align="left"><p>選取此核取方塊以啟用已發佈的應用程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>顯示名稱</p></td>
<td align="left"><p>使用者&#39;s Windows [開始] 功能表中的快捷方式名稱。</p>
<div class="alert">
<strong>注意</strong><br/><p>顯示名稱 <strong> 不 </strong> 區分大小寫。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>已發佈的應用程式的描述，當使用者&#39;s 滑鼠游標移至快捷方式上方時，就會顯示為工具提示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>命令列</p></td>
<td align="left"><p>在 MED-V 工作區中用來執行應用程式的命令。 完整路徑是必要的，而且參數可以與任何其他 Windows 命令一樣，以類似的方式傳遞到應用程式。</p>
<p>在 revertible med-v 工作區中，您可以使用 MapNetworkDrive 語法、 &quot; <em> MapNetworkDrive &lt; 磁片磁碟機 &gt; &lt; 路徑 &gt; </em> &quot; （例如， &quot; <em> MapNetworkDrive t： \tux\date） </em> &quot; 來對應網路磁碟機。</p>
<p>例如，若要發佈 Windows 資源管理器，請使用下列語法： &quot; <em> c： &lt; /em &gt; &quot; 或 &quot; <em> c：\windows </em> 。&quot;</p>
<div class="alert">
<strong>注意</strong><br/><p>若要使用名稱解析，您必須執行下列其中一項操作：</p>
</div>
<div>

</div>
<ul>
<li><p>在 base MED-V 工作區圖像中設定 DNS。</p></li>
<li><p>確認主機中定義了 DNS 解析，並將其設定為使用主機 DNS。</p></li>
<li><p>使用 IP 來定義網路磁碟機。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>如果路徑包含空格，整個路徑必須以引號括住。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>路徑不應該以反斜線（）結尾。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>[開始] 功能表</p></td>
<td align="left"><p>選取此核取方塊，即可在使用者&#39;s Windows [開始] 功能表中建立應用程式的快捷方式。</p></td>
</tr>
</tbody>
</table>



所有發佈的應用程式會顯示為 Windows [**開始**] 功能表中的快捷方式（[**啟動 &gt; 所有程式] &gt; med-v-V 應用程式**）。

## 如何從 MED-V 工作區移除已發佈的應用程式


**從 MED-V 工作區移除應用程式**

1.  按一下 MED-V 工作區。

2.  在 [**應用程式**] 窗格的 [**已發佈的應用程式**] 區段中，選取要移除的應用程式。

3.  按一下 [**移除**]。

    應用程式會從已發佈的應用程式清單中移除。

4.  在 [**原則**] 功能表上，選取 [**確認**]。

## 如何將發佈的功能表新增至 MED-V 工作區


**將已發佈的功能表新增至 MED-V 工作區**

1.  按一下要設定的 MED-V 工作區。

2.  在 [**應用程式**] 窗格的 [**已發佈的功能表**] 區段中，按一下 [**新增**] 以新增功能表。

3.  如下表所述設定功能表屬性。

4.  在 [**原則**] 功能表上，選取 [**確認**]。

**已發佈的功能表屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>啟用</p></td>
<td align="left"><p>選取此核取方塊以啟用已發佈的功能表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>顯示名稱</p></td>
<td align="left"><p>使用者&#39;s Windows [開始] 功能表中的快捷方式名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>描述，當使用者&#39;s 滑鼠游標移到快捷方式上時，就會顯示為工具提示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作區中的資料夾</p></td>
<td align="left"><p>選取要發佈的資料夾，其中包含資料夾中所有應用程式的功能表。</p>
<p>顯示的文字是 [程式] 資料夾中的相對路徑。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果保留空白，主機上的所有程式將會發佈為功能表。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



所有已發佈的功能表都會顯示為 Windows [**開始**] 功能表中的快捷方式（[**啟動 &gt; 所有程式] &gt; med-v-V 應用程式**）。 您可以在 [開始] 功能表的 [**快速鍵] 資料夾**欄位中變更快捷方式的名稱。

**注意**  
設定兩個 MED-V 工作區時，建議您為 [開始] 功能表快捷方式資料夾設定不同的名稱。



## 如何從 MED-V 工作區移除已發佈的功能表


**從 MED-V 工作區移除已發佈的功能表**

1.  按一下 MED-V 工作區。

2.  在 [**應用程式**] 窗格的 [**已發佈的功能表**] 區段中，選取要移除的功能表。

3.  按一下 [**移除**]。

    功能表隨即從已發佈的功能表清單中移除。

4.  在 [**原則**] 功能表上，選取 [**確認**]。

## 從用戶端上的命令列執行已發佈的應用程式


系統管理員可以使用下列命令，從任何位置（例如桌面快捷方式）執行已發佈的應用程式：

``` syntax
"<Install path>\Manager\KidaroCommands.exe" /run "<published application name>" "<MED-V workspace name>"
```

**注意**  
在其中定義已發佈之應用程式的 MED-V 工作區，必須執行。



## 相關主題


[如何使用進階設定來編輯已發行的應用程式](how-to-edit-a-published-application-with-advanced-settings.md)

[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)









